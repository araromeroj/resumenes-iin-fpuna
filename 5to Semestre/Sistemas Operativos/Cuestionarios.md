## Cuestionario de Contenedores LXC (Proxmox)

### Bloque A: Fundamentos de LXC

1. **¿Qué es un contenedor LXC y qué comparte con el nodo Proxmox? ¿Qué aísla y con qué mecanismos del kernel?**
   Un contenedor LXC es una tecnología de virtualización a nivel de sistema operativo. Comparte directamente el kernel de Linux con el nodo anfitrión (Proxmox). Aísla el espacio de usuario, procesos, usuarios, red y sistema de archivos utilizando los mecanismos nativos del kernel Linux: **Namespaces** (para aislamiento de visibilidad) y **Control Groups / cgroups** (para limitación y control de recursos).

2. **Explique qué son los namespaces y los cgroups, y dé un ejemplo de cada uno en este laboratorio.**
   - **Namespaces:** Aíslan lo que un proceso puede "ver" en el sistema. *Ejemplo:* El PID namespace permite que un contenedor tenga su propio proceso PID 1 (`init`/`systemd`) totalmente independiente del PID 1 del nodo Proxmox.
   - **cgroups (Control Groups):** Limitan y miden la cantidad de recursos de hardware que un grupo de procesos puede "consumir". *Ejemplo:* Limitar un contenedor a 1 core de CPU y 512 MB de memoria RAM desde Proxmox.

3. **¿Qué es una plantilla (`vztmpl`) y para qué sirve antes de crear un contenedor?**
   Es un archivo comprimido (`.tar.xz` / `.tar.gz`) que contiene la estructura básica del sistema de archivos de una distribución Linux (como Alpine, Debian o Ubuntu) en espacio de usuario. Sirve como la imagen base para desplegar y poner en marcha un nuevo contenedor LXC en segundos sin necesidad de ejecutar un proceso de instalación interactivo.

4. **¿Qué diferencia hay entre un contenedor privilegiado y uno no privilegiado? ¿Cuál conviene y por qué?**
   - **Privilegiado:** El UID 0 (`root`) dentro del contenedor coincide directamente con el UID 0 (`root`) en el nodo anfitrión, permitiendo acceso completo a las llamadas del sistema del kernel.
   - **No privilegiado:** El UID 0 dentro del contenedor se mapea a un UID sin privilegios (ejemplo: UID 100000) en el nodo anfitrión.
   > [!TIP]
   > **Recomendación:** Conviene usar contenedores **NO privilegiados** por razones de seguridad, ya que si un atacante logra escapar del contenedor, solo tendrá permisos de un usuario sin privilegios en el nodo Proxmox.

5. **¿En qué se parecen y en qué se diferencian un contenedor LXC y un contenedor Docker/Podman (que ya usan los servicios del laboratorio)?**
   - **Semejanzas:** Ambos son contenedores basados en Linux que comparten el kernel del host mediante namespaces y cgroups, ofreciendo ejecuciones livianas.
   - **Diferencias:** LXC es un contenedor de sistema (*System Container*) que ejecuta una distribución completa con su propio sistema de init/services (similar a una VM). Docker/Podman son contenedores de aplicación (*Application Containers*) diseñados para ejecutar un único proceso o aplicación en primer plano de forma efímera.

---

### Bloque B: La Consola PCT (Enter y Exec)

1. **¿Qué información entrega `pct list`? Interprete las columnas VMID, Status y Name.**
   El comando `pct list` muestra la lista de contenedores LXC configurados en el nodo Proxmox.
   - **VMID:** Identificador numérico único asignado al contenedor (ej. `100`, `254`).
   - **Status:** Estado operativo actual del contenedor (`running` o `stopped`).
   - **Name:** Nombre de host o etiqueta identificativa asignada al contenedor (ej. `s.demo.lan`, `c.demo.lan`).

2. **¿Cuál es la diferencia entre `pct enter <vmid>` y `pct exec <vmid> -- <comando>`? Dé un caso de uso para cada uno.**
   - `pct enter <vmid>`: Abre un shell interactivo dentro del contenedor, cambiando las variables de entorno al contexto interno. *Caso de uso:* Tareas de administración manual e inspección interactiva dentro del contenedor.
   - `pct exec <vmid> -- <comando>`: Ejecuta un único comando o script dentro del contenedor desde la consola del host sin abrir un shell interactivo. *Caso de uso:* Automatización de tareas, monitoreo o scripts masivos ejecutados desde el nodo Proxmox.

3. **¿Por qué `pct exec` es el adecuado para scripts y `pct enter` para trabajo interactivo?**
   `pct exec` es no interactivo, retorna el código de salida (`$?`) del comando ejecutado y redirige limpiamente la salida estándar (`stdout`/`stderr`), lo que permite procesar la información en scripts bash. `pct enter` requiere asignación de una pseudo-terminal (TTY) interactiva para que un usuario digite comandos manualmente.

4. **¿Cómo se consulta la configuración de un contenedor con `pct config` y de dónde la toma?**
   Se consulta ejecutando `pct config <vmid>`. Toma los datos leyendo directamente el archivo de texto de configuración almacenado en la ruta `/etc/pve/lxc/<vmid>.conf`.

5. **¿Qué archivo guarda la configuración de un contenedor en el nodo y por qué está en `/etc/pve/`?**
   La guarda el archivo `/etc/pve/lxc/<vmid>.conf`. Está dentro de `/etc/pve/` porque corresponde al sistema de archivos en clúster de Proxmox (Pmxcfs), el cual replica automáticamente la configuración entre todos los nodos del clúster de manera síncrona.

---

### Bloque C: Recursos, Red y Persistencia

1. **¿Cómo se asignan (`pct set`) y cómo se comprueban desde dentro (`nproc`, `free -m`) la CPU y la memoria de un LXC?**
   - **Asignación en el nodo:**
     ```bash
     pct set <vmid> -cores 2 -memory 1024
     ```
   - **Comprobación interna:** Dentro del LXC se ejecuta `nproc` para ver el número de núcleos asignados y `free -m` para comprobar la memoria RAM y Swap disponible en Megabytes.

2. **¿Cómo se amplía el disco de un contenedor (`pct resize`) y cómo se verifica el cambio desde dentro (`df -h /`)?**
   - **Ampliación en el nodo:**
     ```bash
     pct resize <vmid> rootfs +5G
     ```
   - **Verificación interna:** Se ejecuta `df -h /` dentro del contenedor para verificar el espacio total montado en el directorio raíz.

3. **¿Qué son `net0` y `net1` en `pct config`, y cómo se ven por dentro del contenedor (`ip -br a`)?**
   - `net0` y `net1` son las interfaces de red virtuales asignadas al contenedor en su configuración de Proxmox.
   - En la salida interna de `ip -br a` dentro del LXC se observan como las interfaces de red `eth0` y `eth1` con sus respectivas direcciones IP y máscaras asignadas.

4. **¿Qué es el bridge (`vmbr0`) y qué papel cumple la interfaz `veth` del contenedor?**
   - **`vmbr0`:** Es un conmutador de red virtual (*Virtual Bridge*) creado en el nodo Proxmox que conecta las interfaces de los contenedores a la red física o lógica.
   - **`veth` (Virtual Ethernet):** Es un par de interfaces virtuales tipo "cable cruzado". Un extremo (`vethXXXiX`) se conecta al bridge `vmbr0` en el host y el otro extremo aparece como la interfaz `ethX` dentro del LXC.

5. **¿Por qué un contenedor tiene dos interfaces en este laboratorio? ¿Qué gana con eso?**
   Tiene dos interfaces (`net0` y `net1`) para lograr segmentación de red. Le permite estar conectado simultáneamente a una red de administración/infraestructura (ej. red de Proxmox/anfitrión) y a una red de producción/servicios (ej. la red del laboratorio `demo.lan`), mejorando el aislamiento y la seguridad.

6. **¿Dónde vive el sistema de archivos de un contenedor y cómo se logra persistencia y respaldo?**
   El sistema de archivos (`rootfs`) vive en un almacenamiento configurado en Proxmox (como ZFS pool, LVM-Thin o directorio local). La persistencia se logra al estar escrito en almacenamiento no volátil en el host, y el respaldo se realiza mediante snapshots de almacenamiento o respaldos completos comprimidos creados con el comando `vzdump`.

---

### Bloque D: Operación y Automatización

1. **Describa el ciclo de vida de un LXC con `pct` (`status`, `start`, `stop`, `shutdown`, `reboot`).**
   - `pct status <vmid>`: Consulta el estado actual (`running`/`stopped`).
   - `pct start <vmid>`: Enciende el contenedor.
   - `pct stop <vmid>`: Fuerza el apagado inmediato del contenedor (equivalente a desenchufar).
   - `pct shutdown <vmid>`: Envía una señal ACPI al contenedor para un apagado limpio y ordenado de los servicios.
   - `pct reboot <vmid>`: Reinicia de forma limpia el contenedor.

2. **¿Qué es un snapshot de LXC y en qué se diferencia de un respaldo (`vzdump`)? ¿Cuándo usaría cada uno?**
   - **Snapshot (`pct snapshot`):** Copia instantánea del estado y punteros de disco del LXC. Es rápido y ligero. Se usa antes de cambios de riesgo o actualizaciones del sistema para hacer rollback inmediato.
   - **Respaldo (`vzdump`):** Archivo comprimido independiente que contiene la copia completa del contenedor y su configuración. Se usa para recuperación ante desastres o migración entre nodos.

3. **¿Cómo automatizaría con `pct exec` una verificación del estado de todos los contenedores del nodo?**
   Mediante un script bash que itere los VMIDs obtenidos con `pct list`:
   ```bash
   for vmid in $(pct list | awk 'NR>1 {print $1}'); do
     echo "--- Estado CT $vmid ---"
     pct exec $vmid -- uptime
   done
   ```

4. **¿Qué riesgos implica que, dentro de un LXC privileged, un usuario sea root? ¿Cómo lo mitiga un contenedor no privilegiado?**
   En un LXC privilegiado, si un usuario comprometido rompe el aislamiento mediante un fallo de kernel, obtiene privilegios de root en el nodo anfitrión. Un contenedor no privilegiado lo mitiga mapeando el UID 0 del contenedor a un UID sin privilegios (ej. 100000) en el host, haciendo que cualquier escape solo le otorgue permisos inofensivos.

5. **Diseñe el flujo, usando sólo la consola del nodo, para reiniciar el servicio Samba de `s.demo.lan` (CT254) y confirmar que quedó arriba.**
   1. Ejecutar el reinicio del servicio:
      ```bash
      pct exec 254 -- systemctl restart smbd
      # o 'rc-service samba restart' si es Alpine
      ```
   2. Verificar que el proceso está activo:
      ```bash
      pct exec 254 -- systemctl status smbd
      ```
   3. Confirmar que el puerto de Samba escucha:
      ```bash
      pct exec 254 -- netstat -tlnp | grep 445
      ```

---

## Cuestionario: LXC vs Máquinas Virtuales (VirtualBox)

### Bloque A: Arquitectura

1. **¿Dónde vive el kernel en un contenedor LXC y dónde en una máquina virtual de VirtualBox?**
   - **LXC:** Vive exclusivamente en el nodo anfitrión (Proxmox); el contenedor no posee kernel propio.
   - **VM (VirtualBox):** Cada máquina virtual ejecuta su propio kernel independiente (*Guest OS*) sobre la emulación del hipervisor.

2. **¿Qué diferencia hay entre el aislamiento por namespaces/cgroups (LXC) y el aislamiento por hipervisor (VirtualBox)?**
   LXC usa aislamiento lógico dentro del propio kernel de Linux mediante límites de visibilidad (namespaces) y recursos (cgroups). VirtualBox usa aislamiento por hardware emulado impulsado por hipervisor y soporte de CPU (VT-x/AMD-V), separando completamente la memoria y las instrucciones del sistema operativo invitado.

3. **¿Por qué se dice que la virtualización por hipervisor emula hardware y la de contenedores no?**
   Porque el hipervisor intercepta las instrucciones y presenta a la VM dispositivos virtuales completos (BIOS/UEFI, CPU virtual, NIC virtual, disco IDE/SATA emulado). Los contenedores LXC interactúan directamente con las llamadas al sistema (*syscalls*) del kernel del host sin capa de emulación de hardware.

4. **¿Por qué el nodo Proxmox con LXC puede ejecutarse, a su vez, dentro de una VM de VirtualBox (virtualización anidada)?**
   Porque Proxmox solo requiere un kernel de Linux funcional para manejar los contenedores LXC. No necesita obligatoriamente ejecutar hipervisores KVM anidados si solo despliega LXC, por lo que corre sin problemas dentro del espacio de usuario de la máquina virtual de VirtualBox.

5. **¿Qué superficie de ataque tiene cada tecnología y cuál es más sensible a una fuga del kernel?**
   LXC tiene una superficie de ataque orientada a las llamadas de sistema (*syscalls*) del kernel compartido, siendo más sensible a vulnerabilidades de kernel (*kernel exploits*) que permiten la fuga hacia el host. Las VMs tienen una superficie de ataque orientada al emulador de hardware, siendo más aisladas y robustas frente a fallos de kernel en el sistema invitado.

---

### Bloque B: Rendimiento y Densidad

1. **¿Qué overhead agrega cada enfoque y por qué el LXC es más liviano?**
   VirtualBox agrega overhead por emulación de hardware, gestión de MMU virtual y ejecución de un kernel invitado completo. LXC agrega un overhead prácticamente nulo (0-1%) porque los procesos corren directamente a la velocidad nativa de la CPU y RAM del host, solo diferenciándose por cgroups y namespaces.

2. **¿Cómo se explica la diferencia de tiempos de arranque entre un LXC y una VM?**
   Una VM debe pasar por la secuencia de inicialización del hardware virtual (POST/BIOS), cargador de arranque (GRUB), inicialización del kernel y arranque de servicios. Un LXC omite la fase de BIOS y kernel; Proxmox solo crea las estructuras cgroups/namespaces e inicia directamente el proceso `init`/`systemd` en milisegundos.

3. **¿Qué evidencia concreta (`uname -r`, `systemd-detect-virt`, `ps`, tiempos) demuestra que el LXC comparte kernel y la VM no?**
   - `uname -r`: En el LXC retorna la versión exacta del kernel del nodo Proxmox.
   - `systemd-detect-virt`: En LXC devuelve `lxc`, en la VM devuelve `oracle` o `kvm`.
   - `ps` en el nodo: Los procesos que corren dentro del LXC son visibles directamente desde el árbol de procesos del nodo Proxmox.

4. **¿Por qué un mismo nodo puede hospedar muchos LXC y bastantes menos VMs equivalentes?**
   Porque los LXC no reservan memoria fija para kernels individuales ni emulación de hardware. Comparten la memoria RAM de manera dinámica y la CPU mediante el planificador del kernel host, permitiendo una mayor densidad de sobreasignación (*overcommit*).

5. **¿Qué pasa con la memoria si dos LXC ejecutan el mismo binario? ¿Y con dos VMs?**
   - **Dos LXC:** El kernel del host puede compartir las páginas de código en memoria de solo lectura de las librerías/binarios compartidos gracias al *Page Cache* de Linux.
   - **Dos VMs:** Cada VM mantiene copias separadas e incomunicadas del binario en sus propios bloques de RAM asignados por el hipervisor.

---

### Bloque C: Red, Almacenamiento y Snapshots

1. **¿Cómo obtiene su red un LXC (`veth` + `vmbr0`) y cómo la obtiene una VM de VirtualBox (NIC virtual)?**
   - **LXC:** Utiliza un par de interfaces de red virtuales `veth`; un extremo está dentro del LXC y el otro está conectado directamente al bridge `vmbr0` del nodo Linux.
   - **VirtualBox:** Emula un controlador de red por software (ej. Intel e1000) que el sistema operativo invitado reconoce mediante un driver de dispositivo virtual.

2. **¿Por qué en este laboratorio cada contenedor tiene dos interfaces y cómo se refleja eso en `pct config`?**
   Cada contenedor tiene dos interfaces para separar el tráfico de administración del tráfico de red de producción. En `pct config` se refleja mediante las directivas `net0:` y `net1:` especificando puentes, VLANs o IPs distintas.

3. **Compare el almacenamiento del LXC (`rootfs` en un storage) con el disco virtual de VirtualBox (`.vdi`).**
   El almacenamiento de LXC es un directorio montado o un volumen de bloques (ZFS/LVM-Thin) accesible directamente desde el sistema de archivos del host. El disco de VirtualBox es un archivo contenedor monolítico propietario (`.vdi`/`.vmdk`) que requiere traducción de lectura/escritura del sistema de archivos interno por parte del hipervisor.

4. **¿Qué diferencia hay entre un snapshot de LXC (`pct snapshot`/`rollback`) y un snapshot de VirtualBox?**
   Ambos congelan el estado del disco. Sin embargo, los snapshots de LXC sobre ZFS o LVM-Thin son casi instantáneos y a nivel de punteros del sistema de archivos local del servidor. Los snapshots de VirtualBox modifican las cadenas de archivos de discos diferenciales (`.vdi`) con mayor impacto en el rendimiento de E/S.

5. **¿Cómo se mueve una imagen o un contenedor entre nodos (`pct pull`/`pct push`, `vzdump`/`pct restore`) y cómo se haría con una VM?**
   - **En LXC:** Se exporta con `vzdump` a un `.tar.zst` y se restaura en el destino con `pct restore`, o se usa la migración en vivo entre nodos Proxmox.
   - **En VM:** Se exporta a formato OVF/OVA o se copia manualmente el archivo de disco `.vdi`/`.qcow2` y se reimporta en el nuevo hipervisor.

---

### Bloque D: Casos de Uso y Decisión

1. **Dé dos casos donde convenga un LXC y dos donde convenga una máquina virtual.**
   - **Conviene LXC:**
     1. Microservicios o servidores web Linux de alta densidad donde el uso de RAM debe ser mínimo.
     2. Entornos de desarrollo/laboratorio donde se requieran arranques e iteraciones instantáneas.
   - **Conviene VM:**
     1. Necesidad de ejecutar sistemas operativos distintos a Linux (ej. Windows Server, FreeBSD).
     2. Entornos multi-tenant con requisitos críticos de aislamiento de seguridad por hardware.

2. **Si necesita ejecutar Windows o FreeBSD sobre el mismo nodo, ¿LXC o VM? Justifique.**
   Se debe utilizar una **Máquina Virtual (VM)**. Los contenedores LXC no pueden ejecutar Windows o FreeBSD porque carecen de emulación de hardware y dependen estrictamente de las llamadas al sistema del kernel de Linux del host.

3. **Si necesita el máximo aislamiento por razones de seguridad, ¿qué elige y por qué?**
   Elijo una **Máquina Virtual**. El aislamiento por hipervisor implementado por hardware (VT-x/AMD-V) proporciona una barrera rígida donde un compromiso del sistema invitado no expone directamente las llamadas del sistema del kernel anfitrión.

4. **¿Por qué el laboratorio `demo.lan` usa contenedores LXC para los servicios y una VM sólo para el nodo Proxmox?**
   Utiliza una VM para el nodo Proxmox para aislar el entorno completo de pruebas dentro del equipo anfitrión del alumno. Utiliza LXC para los servicios internos para optimizar los recursos de RAM y CPU de la máquina física, permitiendo ejecutar múltiples servicios simultáneos con alto rendimiento.

5. **Diseñe, usando la consola del nodo, el flujo completo para crear un LXC nuevo, desplegar un servicio y respaldarlo (indique los comandos `pct`).**
   1. Crear el contenedor con plantilla Alpine/Debian:
      ```bash
      pct create 300 local:vztmpl/alpine-3.18.tar.xz -storage local-lvm -memory 512 -cores 1 -net0 name=eth0,bridge=vmbr0,ip=dhcp
      ```
   2. Iniciar el contenedor:
      ```bash
      pct start 300
      ```
   3. Desplegar un servicio (ejemplo Nginx):
      ```bash
      pct exec 300 -- apk add nginx
      pct exec 300 -- rc-service nginx start
      ```
   4. Crear un respaldo completo del contenedor:
      ```bash
      vzdump 300 --compress zstd --mode snapshot --storage local
      ```

---

## Parte 2: Cuestionario de Sistemas Operativos

### Bloque A: Usuarios (Locales y de Dominio)

1. **¿Cómo determino la cantidad de usuarios locales en el servidor `s.demo.lan`? ¿Y la cantidad de usuarios del dominio?**
   - **Usuarios locales:** Leyendo el archivo de cuentas del sistema mediante `cat /etc/passwd | wc -l` o usando `getent passwd`.
   - **Usuarios del dominio:** Ejecutando dentro del contenedor del controlador de dominio:
     ```bash
     docker exec samba-dc samba-tool user list | wc -l
     ```

2. **Los usuarios que se agregan al dominio: ¿son agregados a la lista de usuarios del win11?**
   No. Los usuarios permanecen centralizados en la base de datos del Active Directory y el sistema win11 los autentica a través de la red cuando intentan iniciar sesión.

3. **Los usuarios que se agregan al dominio: ¿son agregados a la lista de usuarios del `s.demo.lan`?**
   No. No se agregan al archivo local `/etc/passwd` del servidor `s.demo.lan`.

4. **Los usuarios que se agregan al dominio: ¿son agregados a la lista de usuarios del `c.demo.lan`?**
   No. Tampoco se escriben en el archivo `/etc/passwd` de `c.demo.lan`; se resuelven dinámicamente mediante el servicio winbind y la capa PAM/NSS.

5. **Si inicio sesión con un usuario de dominio en `c.demo.lan`: ¿qué pasa si uso los utilitarios propios de Linux para cambiar la contraseña (`passwd`)?**
   El comando `passwd` tradicional de Linux falla o solo modifica la pila de autenticación PAM local; no actualiza la contraseña centralizada almacenada en el Active Directory.

6. **¿Cómo puedo cambiar la contraseña de un usuario de dominio? (mencione al menos dos vías)**
   - **Vía 1 (Consola Web):** Desde la interfaz de administración `http://192.168.56.254:8888/smb/` editando la cuenta en el panel.
   - **Vía 2 (Línea de comandos en Linux):** Solicitando un ticket Kerberos con `kinit usuario@DEMO.LAN` y ejecutando posteriormente `kpasswd`.
   - **Vía 3 (Windows):** Presionando <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Supr</kbd> y seleccionando "Cambiar contraseña" dentro de la sesión de dominio en win11.

7. **¿Cuántos usuarios tiene el servidor win11?**
   Posee únicamente sus cuentas locales del sistema (como Usuario y Administrador), más las cuentas de dominio del Active Directory que se validan en él vía red.

8. **¿Dónde se almacenan las cuentas locales y dónde las del dominio?**
   - **Cuentas locales:** En los archivos `/etc/passwd` y `/etc/shadow` de cada equipo Linux (o la base de datos SAM local de Windows).
   - **Cuentas del dominio:** Centralizadas en la base de datos de Active Directory (Samba 4) en el contenedor `samba-dc` del servidor `s.demo.lan`.

9. **¿Qué diferencia hay entre `/etc/passwd` y `/etc/shadow`? ¿Por qué las contraseñas no están en `/etc/passwd`?**
   `/etc/passwd` es de lectura pública y guarda metadatos del usuario (UID, GID, home, shell). `/etc/shadow` es accesible solo por `root` y almacena los hashes cifrados de las contraseñas. No se incluyen en `/etc/passwd` para evitar que usuarios no privilegiados realicen ataques de fuerza bruta sobre los hashes.

10. **¿Qué comando permite listar los usuarios del AD desde el cliente `c.demo.lan`? ¿Por qué no aparecen con `cat /etc/passwd`?**
    - **Comando:** `wbinfo -u` (o `getent passwd`).
    - **Razón:** No aparecen en `/etc/passwd` porque las cuentas no existen como archivos locales en el cliente, sino que se consultan en tiempo real al Active Directory.

11. **¿Por qué un usuario creado en el AD no necesita ser creado de nuevo en cada equipo del dominio?**
    Porque la autenticación se encuentra centralizada en el controlador de dominio Samba 4. Cualquier equipo unido al dominio delega la validación de credenciales a dicho servidor central.

---

### Bloque B: Contraseñas y Políticas

1. **¿Dónde se aplica la política de contraseñas (longitud, complejidad, caducidad) para los usuarios de dominio?**
   Se configura y aplica de forma centralizada en el controlador de dominio Active Directory (`samba-dc`).

2. **¿Qué diferencia hay entre autenticación y autorización? Dé un ejemplo con el AD.**
   - **Autenticación:** Verificación de la identidad del usuario (*Ejemplo:* comprobar que la contraseña del usuario `demo` es correcta).
   - **Autorización:** Verificación de los permisos del usuario (*Ejemplo:* comprobar si el grupo "Domain Users" al que pertenece `demo` tiene permisos de lectura sobre una carpeta compartida).

3. **¿Qué es Kerberos y qué papel cumple `kinit`/`kpasswd`?**
   Kerberos es el protocolo de autenticación por tickets seguro del dominio. `kinit` se utiliza para solicitar y autenticar un ticket inicial TGT, mientras que `kpasswd` utiliza ese ticket para cambiar la contraseña en el directorio.

---

### Bloque C: Servicios y Puertos

1. **¿Cómo verifico la disponibilidad de los servicios desde el equipo anfitrión?**
   - `ping`: Verificar conectividad de red (`ping 192.168.56.254`).
   - `nc` / `nmap`: Comprobar el estado de los puertos (`nc -zv 192.168.56.254 8081`).
   - `curl`: Validar la respuesta HTTP del servicio (`curl -I http://192.168.56.254:8081`).

2. **¿Cómo identifico qué puertos TCP están abiertos en el servidor `s.demo.lan`?**
   Ejecutando `netstat -tlnp` (o `ss -tlnp`) en la terminal del servidor o inspeccionando la columna `PORTS` en la salida de `docker ps`.

3. **Desde `c.demo.lan`: ¿cómo puedo identificar qué puertos están alcanzables?**
   Mediante un bucle en consola usando netcat:
   ```bash
   for p in 389 445 8081 8888; do nc -z -w2 192.168.56.254 $p && echo "$p abierto"; done
   ```

4. **¿Cuál es la diferencia entre que un puerto esté abierto/en escucha y que esté alcanzable?**
   - **Abierto / En escucha:** Un servicio dentro del servidor está preparado para aceptar conexiones en ese puerto.
   - **Alcanzable:** Las reglas de red, ruteo y cortafuegos permiten que un cliente externo logre conectarse exitosamente a ese puerto.

5. **¿Cómo compruebo que el servicio responde a nivel de aplicación y no solo a nivel de red? (p. ej. `curl -w "%{http_code}"`)**
   Ejecutando una consulta de aplicación como:
   ```bash
   curl -s -o /dev/null -w "%{http_code}\n" http://192.168.56.254:8081
   ```
   y verificando que el código devuelto sea un estado válido como `200 OK`.

6. **¿Qué es un contenedor y por qué su puerto puede no coincidir con el del servicio interno?**
   Un contenedor es un entorno de ejecución aislado. Sus puertos pueden no coincidir con los internos debido al mapeo de red (NAT/Bridge) que traduce un puerto expuesto del sistema host hacia el puerto nativo del contenedor (ejemplo: `-p 8081:80`).

7. **¿Qué puerto usa LDAP y cuál LDAPS? ¿Por qué Samba exige TLS para el bind simple?**
   LDAP utiliza el puerto **389** y LDAPS el puerto **636**. Samba exige TLS para evitar el envío de contraseñas e información de autenticación en texto plano sobre la red.

8. **¿Qué es DNS y por qué win11 debe usar la IP del DC como servidor DNS para unirse al dominio?**
   DNS se encarga de la resolución de nombres a direcciones IP. win11 requiere usar el DNS del DC para localizar los registros SRV específicos que identifican los servicios de Active Directory y Kerberos.

9. **¿Qué es NTP y por qué una diferencia de hora mayor a 5 minutos rompe la autenticación Kerberos?**
   NTP es el protocolo de sincronización de tiempo. Kerberos requiere sincronización horaria para incluir marcas de tiempo en los tickets y prevenir ataques de denegación o repetición (*replay attacks*); si la diferencia supera los 5 minutos, los tickets se consideran inválidos.

---

### Bloque D: Procesos, IA y Automatización

1. **¿Qué es un proceso y qué información muestra `ps`/`top` (PID, usuario, CPU, memoria)?**
   Un proceso es un programa en ejecución. Los comandos `ps`/`top` muestran su identificador único (**PID**), el **usuario** propietario, el porcentaje de uso de procesador (**%CPU**) y el consumo de memoria RAM (**%MEM**).

2. **¿Qué ventaja aporta usar IA (`opencode`) para desarrollar una aplicación en el laboratorio?**
   Permite generar código base, plantillas HTML y archivos de configuración (como Dockerfile) de forma rápida mediante lenguaje natural.

3. **¿Por qué es riesgoso ejecutar instrucciones generadas por IA sin revisarlas? (seguridad, permisos, credenciales)**
   Porque la IA puede sugerir comandos destructivos, asignar permisos inseguros (como `chmod 777`) o incluir credenciales expuestas sin validación.

4. **¿Qué es un archivo de configuración de agente (p. ej. `AGENTS.md`) y para qué sirve?**
   Es un documento que define el contexto, limitaciones, herramientas y comportamiento que debe seguir un agente de IA durante la automatización de tareas.

5. **¿Qué diferencia hay entre un servicio (daemon) y un proceso común? Dé dos ejemplos del laboratorio.**
   Un servicio (*daemon*) corre en segundo plano continuamente sin interfaz ni terminal asociada.
   - **Ejemplos de daemon:** `dockerd`, `sshd`.
   - **Ejemplos de proceso común:** `ls`, `curl`.

6. **¿Cómo se asegura la persistencia de los datos de un contenedor y por qué es necesaria?**
   Se asegura mediante volúmenes (`docker volume` / `-v`). Es necesaria porque la capa de escritura de los contenedores es efímera y los datos se pierden al eliminar el contenedor.

7. **¿Qué es un usuario de servicio (p. ej. `svc-adctl`) y por qué conviene usarlo en lugar del Administrator?**
   Es una cuenta dedicada exclusivamente a tareas automatizadas con permisos acotados, evitando exponer las credenciales con privilegios globales del Administrator.

---

## Parte 4: Cuestionario de Docker / Podman

### Bloque A: Fundamentos

1. **¿Qué es un contenedor y en qué se diferencia de una máquina virtual?**
   Un contenedor aísla procesos compartiendo el kernel del sistema operativo anfitrión. Una máquina virtual emula un hardware completo ejecutando un sistema operativo independiente con su propio kernel sobre un hipervisor.

2. **¿Cuál es la diferencia entre una imagen y un contenedor?**
   Una **imagen** es una plantilla de solo lectura estática. Un **contenedor** es una instancia activa y ejecutable creada a partir de esa imagen.

3. **¿Qué es un Dockerfile/Containerfile y para qué sirve cada instrucción (`FROM`, `COPY`, `RUN`, `EXPOSE`, `CMD`)?**
   Es la receta de construcción de una imagen.
   - `FROM`: Define la imagen base.
   - `COPY`: Copia archivos del host al contenedor.
   - `RUN`: Ejecuta comandos durante la creación de la imagen.
   - `EXPOSE`: Informa los puertos que utiliza la aplicación.
   - `CMD`: Define el comando por defecto al arrancar el contenedor.

4. **¿Qué diferencia hay entre Docker y Podman en cuanto a daemon y privilegios?**
   Docker requiere un demonio central residente (`dockerd`) ejecutado con privilegios de root. Podman funciona sin demonio (*daemonless*) y admite la ejecución sin privilegios de administrador (*rootless*).

5. **¿Qué significa "rootless" y qué ventaja de seguridad aporta?**
   Significa ejecutar contenedores bajo el espacio de usuarios sin privilegios del host. Si un contenedor es vulnerado, el atacante no obtiene privilegios de administrador sobre el sistema anfitrión.

6. **¿Qué es un volumen y por qué se usa en lugar de escribir dentro del contenedor?**
   Es un directorio administrado fuera de la capa interna del contenedor. Se utiliza para preservar los datos de forma permanente en el host aunque el contenedor se detenga o elimine.

---

### Bloque B: Red y Puertos

1. **¿Qué significa `-p 8080:8080`? ¿Cuál número es el puerto del host y cuál el del contenedor?**
   El primer número (`8080`) es el puerto abierto en la máquina host. El segundo número (`8080`) es el puerto interno en el que escucha el contenedor.

2. **¿Por qué en el servidor hay que elegir un puerto libre (evitar 8081, 8888, 9999)?**
   Porque esos puertos ya están ocupados por otros servicios en ejecución en `s.demo.lan` (`speedtest`, `samba-admin`, `wa-sim`) y se generaría un conflicto de red.

3. **¿Qué diferencia hay entre `network_mode: host` y el mapeo de puertos por bridge? ¿Por qué el DC de Samba usa host?**
   Bridge aísla la red del contenedor y requiere la publicación explícita de puertos. Host hace que el contenedor comparta la interfaz de red directa del servidor. Samba DC usa host debido a la cantidad y complejidad de puertos requeridos para Active Directory (53, 88, 389, 445, 636).

4. **¿Cómo se comunican dos contenedores en la misma red de contenedores?**
   Se comunican mediante el uso del nombre del contenedor como nombre de dominio gracias al servicio DNS integrado en el motor de contenedores.

---

### Bloque C: Imágenes y Distribución

1. **¿Cómo se construye una imagen y cómo se le asigna un nombre y etiqueta (`-t`)?**
   Se construye mediante el comando `docker build`:
   ```bash
   docker build -t nombre:etiqueta .
   # Ejemplo: docker build -t mi-web:1.0 .
   ```

2. **¿Cómo se transfiere una imagen a otra máquina sin un registry? (p. ej. `save`/`load`)**
   1. Exportando la imagen a un archivo:
      ```bash
      podman save -o imagen.tar mi-web:1.0
      ```
   2. Transfiriéndola mediante SCP:
      ```bash
      scp imagen.tar root@192.168.56.254:/root/
      ```
   3. Importándola en la máquina destino:
      ```bash
      docker load -i imagen.tar
      ```

3. **¿Qué es un registry y qué función cumple `push`/`pull`?**
   Es un servidor centralizado para almacenar y compartir imágenes OCI. `push` sube una imagen al servidor y `pull` la descarga.

4. **¿Qué es el formato OCI y por qué importa para mover imágenes entre Docker y Podman?**
   Es el estándar abierto (*Open Container Initiative*) para imágenes y tiempos de ejecución. Permite que las imágenes construidas en Podman se puedan desplegar directamente en Docker sin modificaciones.

---

### Bloque D: Operación

1. **¿Cómo se revisan los logs y se ejecuta un comando dentro de un contenedor (`logs`, `exec`)?**
   - **Revisar logs:** `docker logs <nombre_contenedor>`
   - **Ejecutar comandos dentro:** `docker exec -it <nombre_contenedor> sh`

2. **¿Qué hace `docker compose` (o `podman-compose`) y cuándo conviene frente a `docker run`?**
   Permite definir y administrar entornos de múltiples contenedores mediante un archivo YAML declarativo. Conviene usarlo cuando una aplicación requiere varios servicios interactuando entre sí.

3. **¿Cómo se garantiza que un contenedor se reinicie tras un reinicio del host?**
   Añadiendo la opción `--restart unless-stopped` al momento de ejecutar el comando `docker run`.

4. **Diseñe el flujo completo desarrollo en `c.demo.lan` -> despliegue en `s.demo.lan` indicando los comandos.**
   1. **Desarrollo en `c.demo.lan`:** Generar los archivos `index.html` y `Dockerfile`.
   2. **Empaquetado:**
      ```bash
      tar czf /tmp/mi-web-src.tgz index.html Dockerfile
      ```
   3. **Transferencia:**
      ```bash
      scp /tmp/mi-web-src.tgz root@192.168.56.254:/root/
      ```
   4. **Construcción en `s.demo.lan`:**
      ```bash
      docker build -t mi-web:1.0 .
      ```
   5. **Despliegue:**
      ```bash
      docker run -d --name mi-web -p 8080:8080 --restart unless-stopped mi-web:1.0
      ```
   6. **Verificación:**
      ```bash
      curl -s http://192.168.56.254:8080
      ```