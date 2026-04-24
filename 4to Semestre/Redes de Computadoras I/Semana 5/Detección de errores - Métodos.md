## 1. Bits de Paridad

>[!info] Funcionamiento
>Se añade un solo bit al final del mensaje para que la suma total de bits "1" sea par (paridad par) o impar (paridad impar). Matemáticamente equivale a realizar una operación **XOR (Exclusive OR - O Exclusivo)** sobre los datos.

- **Características:** La distancia de Hamming es de 2.
- **Ventajas:** Es el método más simple y requiere muy pocos recursos computacionales.
- **Desventajas:** Solo detecta errores que afecten a una cantidad impar de bits (1, 3, 5...); si cambian 2 bits (un número par), el error pasa desapercibido.

## 2. Checksums (Sumas de Comprobación)

>[!info] Funcionamiento
>El emisor trata los datos como una secuencia de palabras de longitud $N$ y realiza una suma módulo $2^N$. El resultado se complementa y se envía junto al mensaje. El receptor suma todas las palabras recibidas; si el resultado no es cero (o todo "1"s según la lógica), hay un error.

- **Características:** Es el estándar en protocolos como **IP (Internet Protocol - Protocolo de Internet)**.
- **Ventajas:** Ofrece una mejor detección que la paridad simple y puede detectar ráfagas de hasta $N$ errores.
- **Desventajas:** Es vulnerable a errores sistemáticos, como la adición accidental de ceros en el mensaje.

## 3. CRC (Cyclic Redundancy Check - Verificación de Redundancia Cíclica)

>[!info] Funcionamiento
>Se basa en el tratamiento de mensajes como polinomios con coeficientes binarios.
>1. **Emisor:** Determina el grado $r$ de un polinomio generador $G(x)$ y anexa $r$ ceros al mensaje $m(x)$.
>2. Divide el mensaje resultante entre $G(x)$ usando aritmética de módulo 2.
>3. Reemplaza los ceros anexados por el residuo de la división, creando una trama perfectamente divisible por $G(x)$.
>4. **Receptor:** Divide la trama recibida por el mismo $G(x)$. Si el residuo es 0, no hay errores; de lo contrario, se rechaza.

- **Características:** Es la técnica más utilizada en **LAN (Local Area Network - Red de Área Local)** como Ethernet y Wi-Fi.
- **Ventajas:** Extremadamente robusto. Detecta todas las ráfagas de error de longitud $L \le r$ y todos los errores de un solo bit si el polinomio tiene más de un término.
- **Desventajas:** Requiere mayor capacidad de procesamiento que los métodos anteriores, aunque suele implementarse eficientemente en hardware.

# Manejo de Errores en Canales Ruidosos

Cuando se detecta un error, los protocolos suelen emplear técnicas de **ARQ (Automatic Repeat Request - Solicitud de Repetición Automática)**. Esto implica que el receptor descarta la trama errónea y, mediante el uso de temporizadores y números de secuencia, el emisor vuelve a transmitir la información hasta recibir una confirmación de recepción correcta. [[Automatic Repeat reQuest - ARQ]].