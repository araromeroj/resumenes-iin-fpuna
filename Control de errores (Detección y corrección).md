Los errores inalámbricos y los bucles locales envejecidos tienen tasas de error que son órdenes de magnitud mayores.
Las estrategias tomadas para el manejo de errores utilizan información adicional añadidas a los datos enviados.
- [i] Los errores se deben a:
	- Distorsión
	- Ruido
	- Atenuación

>[!important] Estrategias de control de errores
>Ambas se basan en **añadir la suficiente información redundante** para que el **receptor** pueda **deducir**:
>1. Lo enviado. [[Control de errores (Detección y corrección)#Códigos de corrección|Códigos de corrección]]
>2. Si se ha producido un error y solicitar una retransmisión. (no identifica dónde se produjo el error). [[Control de errores (Detección y corrección)#Códigos de detección|Códigos de detección]]
### Tipo de error
Como ningún modelo es 100% efectivo, hay que considerar el tipo de error producido.
1. Variaciones en **ruido térmico:** producen errores uniformemente distribuidos.
2. **Errores impulsivos:** producen errores de ráfaga (son más difíciles de corregir que los errores aislados).

## Códigos de corrección (FEC - Forward Error Connection)
- Se utilizan en canales ruidosos porque las retransmisiones tienen la misma probabilidad de error que la primera transmisión.
- Usos: [[2. Capa Física]], [[2. Capa de Enlace de Datos]] y capas superiores.

>[!tip] Los diferentes tipos de corrección de errores son:
>1. Código de Hamming
>2. Código convolucionales binarios
>3. Códigos Reed-Solomon
>4. Códigos de comprobación de paridad de baja densidad

- **Código de bloques:** los **r** bits de comprobación se calculan en función a los **m** bits de datos asociados.
- **Código sistemático:** los **m** bits de datos se envían a la vez que los de control, en lugar de codificarse antes de los enviados.
- **Código lineal:** los **r** bits de control se calculan como una función lineal de los **m** bits de datos.

==El más utilizado es el OR exclusivo o XOR o la **suma de módulo 2**==

- [I] **Codeword (palabra codificada):** unidad de n bits que contiene datos y bits de comprobación.
- [I] **Tasa de codificación:** es la fracción de la codificación que contiene información no redundante ($m/n$).
	- ($1/2$) en canal ruidoso
	- ($1$) en canales de alta calidad

## Códigos de detección

---
# Enlaces relacionados
- Siguiente nota: [[Código de Hamming]]
- 