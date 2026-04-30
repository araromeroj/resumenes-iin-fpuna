La clasificación de las redes según su **alcance geográfico** permite organizar las tecnologías desde el ámbito personal hasta el global.

>[!important] No olvidar
>Usar potencias de $2$ para **almacenamiento**
>Usar potencias de $10$ para **tasas de bits**

| Alcance           | Tipo de red |
| ----------------- | ----------- |
| Vecindad Personal | PAN         |
| Edificio o campus | LAN         |
| Ciudad            | MAN         |
| País              | WAN         |
| Planeta           | Internet    |
| Almacenamiento    | SAN         |

### 1. PAN (Personal Area Network) - Red de Área Personal

- **Alcance:** Unos pocos metros, limitado al entorno de una **persona**.
- **Características:** Conecta dispositivos periféricos (auriculares, relojes inteligentes, ratones) a un equipo principal como un smartphone o una laptop, poca tasa de bits.
- **Ejemplo:** La tecnología **Bluetooth** es el estándar inalámbrico más común para formar una PAN.

- [*] **PAN - Personal area network:** red de área personal
### 2. LAN (Local Area Network) - Red de Área Local

- **Alcance:** Un edificio o un **campus** universitario/corporativo.
- **Características:** Son redes privadas de **alta velocidad** (desde 100 Mbps hasta 40 Gbps) con baja latencia y pocos errores de transmisión.
- **Subtipo (Redes Domésticas):** Un tipo de LAN diseñada para hogares que debe ser fácil de instalar, segura y permitir la interacción entre dispositivos diversos como Smart TVs y sensores de IoT.
- **Tecnologías:** **Ethernet** 802.3 (cableada) y **Wi-Fi** 802.11 (inalámbrica) son las dominantes.

- [*] **LAN - Local area networks:** redes de área local
- [*] **VLAN - Virtual local area networks:** redes virtuales de área local

Podría interesar: [[1. Bases Teóricas de la Transmisión de Datos]], [[Medios Guiados de Transmisión]]
### 3. MAN (Metropolitan Area Network) - Red de Área Metropolitana

- **Alcance:** Una **ciudad** entera.
- **Características:** Interconecta múltiples LANs dentro de un área urbana. Un ejemplo clásico son las redes de **televisión por cable**, que originalmente distribuían video y luego evolucionaron para proveer Internet de banda ancha a toda una ciudad.
- **Otras tecnologías:** El estándar **WiMAX** (IEEE 802.16) fue diseñado como una opción inalámbrica para este nivel.

- [*] **MAN- Metropolitan area networks:** redes de área metropolitana
### 4. WAN (Wide Area Network) - Red de Área Extensa

- **Alcance:** Un **país o continente**.
- **Características:** Utiliza líneas de transmisión proporcionadas por empresas de telecomunicaciones y elementos de conmutación llamados **routers** para mover paquetes a grandes distancias.
- **Componentes:** Se divide en **hosts** (máquinas de usuario) y la **subred de comunicación** (líneas y enrutadores).
- **Variantes:** Incluyen redes de telefonía móvil, redes por satélite y **VPN** (redes virtuales que corren sobre Internet).
- **Estándar:** WiMax IEEE 802.16

El host se encarga de los aspectos de aplicación, mientras que la subred (routers y líneas) se encarga de la comunicación pura. Para conectarse a Internet, un host debe unirse a un proveedor de servicios (ISP) para intercambiar paquetes con otros hosts.

- [*] **LTE - Long term evolution:** evolución a largo plazo
- [*] **WAN - Wide area networks:** redes de área extensa
### 5. Internetwork (Red de Redes) o Interred
- [I] **Inter-red o Internet:** colección de redes interconectadas. Interconexión de redes operadas independientemente, conectando una LAN y una WAN o conectando dos LANSs. La red combina subredes y hosts. Una subred puede ser ocmo una ISP y una inter-red puede ser como una WAN.
- [I] **Gateways:** hacen una conexión entre dos o más redes.
- **Alcance:** El **planeta** entero.
- **Definición:** Es un conjunto de redes independientes (LANs y WANs) interconectadas para funcionar como una unidad global mediante dispositivos de traducción llamados **pasarelas** o routers.
- **El ejemplo máximo:** **Internet**, que conecta a millones de dispositivos autónomos utilizando la pila de protocolos TCP/IP.

---

- [I] **Host:** computadoras de los usuarios finales destinadas a ejecutar programas de aplicación.
- [I] **Conmutador o switch:** dispositivo especializado en la [[2. Capa de Enlace de Datos|capa de enlace de datos]] que interconecta computadoras o incluso otros conmutadores mediante enlaces punto a punto.
- [I] **Router o enrutador:** dispositivo de interconexión que opera en la [[3. Capa de Red]] y tiene la función de conectar dos o más líneas de transmisión o redes diferentes.

---
# Enlaces relacionados
- Siguiente nota: [[Internet]]
- [[1. Redes - Introducción]]