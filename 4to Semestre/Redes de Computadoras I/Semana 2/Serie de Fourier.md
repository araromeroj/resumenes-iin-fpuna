## 1. ¿Qué es la Serie de Fourier?

Imagina que una señal compleja (como el sonido de una guitarra o una onda cuadrada electrónica) es un batido de frutas. La Serie de Fourier es la "receta" que te dice exactamente qué frutas (frecuencias puras) y en qué cantidad (amplitudes) necesitas mezclar para recrear ese batido.

En términos matemáticos, el teorema de Fourier establece que **cualquier función periódica puede expresarse como una suma infinita de funciones oscilantes simples** (senos y cosenos).

En lugar de ver una señal en el **dominio del tiempo** (cómo cambia la amplitud a medida que avanzan los segundos), Fourier nos permite verla en el **dominio de la frecuencia** (qué frecuencias específicas la componen).

---

### 2. Su aplicación en las Señales de Ancho de Banda

El concepto de "ancho de banda" (bandwidth) y las Series de Fourier van de la mano en el mundo de las telecomunicaciones, el procesamiento de audio y las redes.

- **Definición de Ancho de Banda:** Es la diferencia entre la frecuencia más alta y la más baja que componen una señal.
    
- **¿Para qué usamos Fourier aquí?** Las señales reales (como tu voz en una llamada telefónica o los datos del WiFi) están compuestas por muchísimas frecuencias. Al aplicar Fourier, obtenemos el espectro de frecuencias de esa señal.
    
- **Diseño de Filtros y Canales:** Los cables, la fibra óptica y el aire físico tienen un límite en la cantidad de frecuencias que pueden transmitir sin distorsionarlas. Al conocer las frecuencias de nuestra señal gracias a Fourier, los ingenieros saben exactamente qué **ancho de banda** necesita un canal para transmitir esa señal correctamente. Si el canal es estrecho, Fourier nos ayuda a calcular qué frecuencias (generalmente las más altas) podemos "cortar" sin perder la información principal.
    

---

### 3. Guía paso a paso para resolver Series de Fourier

Para una función periódica $f(t)$ con un periodo $T$, la Serie de Fourier trigonométrica se define como:

$$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left[ a_n \cos(n \omega_0 t) + b_n \sin(n \omega_0 t) \right]$$

Donde $\omega_0$ es la frecuencia angular fundamental: $\omega_0 = \frac{2\pi}{T}$.

Para resolverla, debes encontrar los coeficientes $a_0$, $a_n$ y $b_n$. Sigue estos pasos:

#### Paso 1: Identificar el periodo ($T$) y la frecuencia angular ($\omega_0$)

Observa la gráfica o la función matemática y determina cada cuánto tiempo se repite exactamente la misma forma. Ese es tu periodo $T$. Luego, calcula $\omega_0$.

#### Paso 2: El truco de oro (Analizar la Simetría)

Antes de integrar, mira si la función es simétrica. Esto te ahorrará muchísimo trabajo:

- **Función Par ($f(t) = f(-t)$):** Hay simetría respecto al eje Y (ej. una onda triangular centrada).
    
    - _Atajo:_ No hay senos. Por lo tanto, $b_n = 0$. Solo calculas $a_0$ y $a_n$.
        
- **Función Impar ($f(-t) = -f(t)$):** Hay simetría respecto al origen (ej. una onda cuadrada invertida).
    
    - _Atajo:_ No hay cosenos ni componente continua. Por lo tanto, $a_0 = 0$ y $a_n = 0$. Solo calculas $b_n$.
        

#### Paso 3: Calcular el coeficiente $a_0$ (Componente Continua / Valor Medio)

Este coeficiente representa el valor promedio de la señal. Si la señal tiene la misma área por encima y por debajo del eje X, este valor será cero.

$$a_0 = \frac{2}{T} \int_{0}^{T} f(t) dt$$

_(Nota: puedes integrar desde $-T/2$ hasta $T/2$ si los límites de tu función son más fáciles de evaluar ahí)._

#### Paso 4: Calcular los coeficientes $a_n$ y $b_n$

Aquí es donde usarás integración (a menudo por partes).

$$a_n = \frac{2}{T} \int_{0}^{T} f(t) \cos(n \omega_0 t) dt$$

$$b_n = \frac{2}{T} \int_{0}^{T} f(t) \sin(n \omega_0 t) dt$$

#### Paso 5: Armar la serie final

Una vez que tengas los resultados de las integrales, simplemente reemplaza $a_0$, $a_n$, $b_n$ y $\omega_0$ en la fórmula general del principio.

---

> **Consejo práctico para las integrales:** Ten a mano una tabla de integrales trigonométricas y recuerda propiedades básicas como $\sin(n\pi) = 0$ y $\cos(n\pi) = (-1)^n$ (para números enteros $n$). Aparecen constantemente al evaluar los límites.

[[Capa Física]]