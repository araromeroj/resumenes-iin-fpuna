## Síntesis Teórica Detallada

La Unidad IV aborda el estudio de los campos magnéticos y sus fuentes, analizando tanto los efectos que estos campos ejercen sobre las cargas eléctricas en movimiento como las leyes fundamentales que gobiernan la generación de magnetismo a partir de corrientes eléctricas.

### 1. El Campo Magnético ($\vec{B}$) e Interacciones Magnéticas

A diferencia de las fuerzas electrostáticas que actúan sobre cargas en reposo, las fuerzas magnéticas actúan únicamente sobre partículas cargadas que se encuentran en movimiento. El campo magnético $\vec{B}$ es una magnitud vectorial presente en el espacio circundante a cualquier carga en movimiento o material magnético.

La fuerza magnética $\vec{F}_B$ ejercida sobre una carga de prueba $q$ que se mueve con una velocidad $\vec{v}$ en el seno de un campo magnético se define matemáticamente mediante el producto vectorial:

$$\vec{F}_B = q (\vec{v} \times \vec{B})$$

Las propiedades fundamentales de esta interacción deducidas de la expresión son:

- La magnitud de la fuerza es proporcional a la carga $q$ y a la rapidez de la partícula.
    
- La dirección de la fuerza $\vec{F}_B$ es siempre perpendicular tanto al vector velocidad $\vec{v}$ como al vector de campo magnético $\vec{B}$.
    
- Si una carga se mueve de forma paralela o antiparalela al campo magnético ($\theta = 0^\circ$ o $\theta = 180^\circ$), la fuerza magnética es nula. La fuerza alcanza su valor máximo cuando el movimiento es completamente perpendicular al campo ($\theta = 90^\circ$).
    
- Una carga negativa experimenta una fuerza en sentido opuesto al que predice la regla de la mano derecha para cargas positivas.
    

La unidad del campo magnético en el Sistema Internacional es el **Tesla (T)**, definido como $1\text{ T} = 1\text{ N} / (\text{A} \cdot \text{m})$.

### 2. Líneas de Campo Magnético y Flujo Magnético ($\Phi_B$)

Las líneas de campo magnético sirven para representar visualmente el campo. A diferencia de las líneas de campo eléctrico (que nacen en cargas positivas y mueren en negativas), las líneas magnéticas siempre forman lazos cerrados continuos que van del polo norte al polo sur por el exterior del imán, y del polo sur al norte por su interior, reflejando la inexistencia de monopolos magnéticos aislados.

El flujo magnético $\Phi_B$ representa el número de líneas de campo que atraviesan una superficie determinada. Para una superficie plana de área $A$ bajo un campo magnético uniforme, se define como:

$$\Phi_B = \vec{B} \cdot \vec{A} = B A \cos\theta$$

Donde $\theta$ es el ángulo entre el vector $\vec{B}$ y el vector normal (perpendicular) a la superficie. Su unidad es el **Weber (Wb)**, equivalente a $1\text{ T} \cdot \text{m}^2$. De acuerdo con la ley de Gauss para el magnetismo, el flujo magnético neto a través de cualquier superficie cerrada es siempre igual a cero: $\oint \vec{B} \cdot d\vec{A} = 0$.

### 3. Movimiento de Partículas Cargadas en un Campo Magnético

Cuando una partícula cargada penetra en una región con un campo magnético uniforme de forma estrictamente perpendicular a las líneas de campo ($\vec{v} \perp \vec{B}$), la fuerza magnética actúa de manera constante perpendicular a la trayectoria. Dado que la fuerza no tiene componente en la dirección del movimiento, no realiza trabajo mecánico y la rapidez de la partícula permanece constante.

Esta fuerza perpendicular constante actúa de forma pura como una fuerza centrípeta, obligando a la partícula a describir un **movimiento circular uniforme**. Si la velocidad inicial de la partícula posee componentes tanto perpendiculares como paralelas al campo, la componente paralela no se ve afectada mientras que la componente perpendicular genera el giro, dando como resultado un **movimiento helicoidal** (en forma de hélice).

### 4. Fuerza Magnética sobre un Conductor con Corriente

Dado que una corriente eléctrica consiste en un flujo de cargas en movimiento, un conductor que transporta corriente inmerso en un campo magnético experimentará una fuerza neta equivalente a la suma vectorial de las fuerzas individuales ejercidas sobre cada portador de carga.

Para un segmento de conductor recto de longitud $L$ y sección transversal uniforme que transporta una corriente constante $I$ en presencia de un campo uniforme $\vec{B}$, la fuerza magnética se expresa como:

$$\vec{F}_B = I (\vec{L} \times \vec{B})$$

Donde el vector $\vec{L}$ tiene una magnitud equivalente a la longitud del segmento conductor y apunta firmemente en la dirección convencional del flujo de la corriente eléctrica.

### 5. Fuentes de Campo Magnético: Ley de Biot-Savart

La ley de Biot-Savart permite calcular el campo magnético total generado en un punto del espacio por una distribución cualquiera de corrientes eléctricas estables. Postula que un elemento diferencial de conductor $d\vec{s}$ que transporta una corriente $I$ genera un campo magnético diferencial $d\vec{B}$ dado por la ecuación:

$$d\vec{B} = \frac{\mu_0}{4\pi} \frac{I (d\vec{s} \times \hat{r})}{r^2}$$

Donde:

- $\mu_0$ es la permeabilidad magnética del vacío, cuyo valor constante es exactamente $4\pi \times 10^{-7}\text{ T} \cdot \text{m/A}$.
    
- $r$ es la distancia lineal desde el elemento de corriente hasta el punto de medición.
    
- $\hat{r}$ es el vector unitario dirigido desde el elemento de corriente hacia el punto de interés.
    

Para hallar el campo magnético total $\vec{B}$, se debe integrar esta expresión a lo largo de toda la geometría del conductor: $\vec{B} = \int d\vec{B}$. Dos aplicaciones de gran relevancia práctica son:

- **Conductor recto largo:** El campo magnético a una distancia $r$ de un alambre conductor infinitamente largo viene dado por $B = \frac{\mu_0 I}{2\pi r}$. Las líneas de campo forman anillos concéntricos alrededor del cable.
    
- **Espira circular de corriente:** En el centro geométrico de una espira circular de radio $R$ que transporta una corriente $I$, el campo magnético posee un valor de $B = \frac{\mu_0 I}{2 R}$ y su dirección es perpendicular al plano de la espira.
    

### 6. Ley de Ampere

La ley de Ampere establece una relación directa entre la componente tangencial de un campo magnético integrada a lo largo de una trayectoria cerrada (denominada espira amperiana) y la corriente neta total que atraviesa la superficie delimitada por dicha trayectoria. Su expresión matemática es:

$$\oint \vec{B} \cdot d\vec{s} = \mu_0 I_{\text{encerrada}}$$

Esta ley resulta de enorme utilidad para calcular de manera sencilla campos magnéticos en sistemas que gozan de un alto grado de simetría geométrica (como cilindros infinitos, solenoides compactos o toroides) , evitando la necesidad de recurrir a las integrales vectoriales complejas de Biot-Savart.

---
## Guía de Fórmulas y Aplicación

### 1. Fuerza Magnética sobre una Carga Móvil

- **Ecuación:** $F_B = |q| v B \sin\phi$
    
- **Variables y Unidades:**
    
    - $F_B$: Magnitud de la fuerza magnética [Newtons, $\text{N}$]
        
    - $q$: Carga eléctrica de la partícula [Culombios, $\text{C}$]
        
    - $v$ o $v$: Rapidez o módulo de la velocidad de la partícula [Metros por segundo, $\text{m/s}$]
        
    - $B$: Magnitud del campo magnético [Teslas, $\text{T}$]
        
    - $\phi$ o $\theta$: Ángulo menor formado entre los vectores $\vec{v}$ y $\vec{B}$ [Grados o Radianes]
        
- **Identificadores en el enunciado:** "calcular la fuerza sobre un protón/electrón", "partícula con velocidad $v$ entra en un campo magnético", "determinar la aceleración experimentada por una carga en un campo magnético".
    

### 2. Radio de la Órbita Circular de una Carga

- **Ecuación:** $r = \frac{m v}{|q| B}$
    
- **Variables y Unidades:**
    
    - $r$: Radio de la trayectoria circular descrita [Metros, $\text{m}$]
        
    - $m$: Masa de la partícula cargada [Kilogramos, $\text{kg}$]
        
    - $v$: Rapidez de la partícula en dirección perpendicular al campo [$\text{m/s}$]
        
    - $q$: Carga de la partícula [$\text{C}$]
        
    - $B$: Intensidad del campo magnético uniforme [$\text{T}$]
        
- **Identificadores en el enunciado:** "describe una trayectoria circular", "región de campo uniforme perpendicular", "calcular el radio de giro", "espectrómetro de masas", "magnetrón de microondas".
    

### 3. Fuerza Magnética sobre un Segmento de Conductor Recto

- **Ecuación:** $F_B = I L B \sin\phi$
    
- **Variables y Unidades:**
    
    - $F_B$: Fuerza ejercida sobre el alambre conductor [$\text{N}$]
        
    - $I$: Intensidad de la corriente eléctrica continua [Amperios, $\text{A}$]
        
    - $L$: Longitud del segmento del conductor inmerso en el campo [Metros, $\text{m}$]
        
    - $B$: Módulo del campo magnético uniforme [$\text{T}$]
        
    - $\phi$: Ángulo existente entre el sentido de la corriente (dirección de $\vec{L}$) y el vector de campo $\vec{B}$.
        
- **Identificadores en el enunciado:** "un cable conductor transporta una corriente", "fuerza por unidad de longitud sobre un alambre", "un segmento recto suspendido en un campo magnético".
    

### 4. Campo Magnético de un Conductor Recto Largo (Ley de Biot-Savart / Ampere)

- **Ecuación:** $B = \frac{\mu_0 I}{2\pi r}$
    
- **Variables y Unidades:**
    
    - $B$: Campo magnético inducido a una distancia radial [$\text{T}$]
        
    - $\mu_0$: Permeabilidad del vacío ($4\pi \times 10^{-7}\text{ T}\cdot\text{m/A}$)
        
    - $I$: Corriente que fluye por el conductor largo [$\text{A}$]
        
    - $r$: Distancia perpendicular medida desde el centro del cable hasta el punto [Metros, $\text{m}$]
        
- **Identificadores en el enunciado:** "alambre conductor largo y recto", "calcular el campo magnético a una distancia de un cable", "conductores paralelos que transportan corrientes".
    

### 5. Ley de Ampere (Integral de Trayectoria Cerrada)

- **Ecuación:** $\oint \vec{B} \cdot d\vec{s} = \mu_0 I_{\text{enc}}$
    
- **Variables y Unidades:**
    
    - $\oint \vec{B} \cdot d\vec{s}$: Integral de línea alrededor de una curva cerrada [$\text{T}\cdot\text{m}$]
        
    - $I_{\text{enc}}$ o $I$: Suma algebraica de las corrientes que perforan la superficie amperiana [$\text{A}$]
        
- **Identificadores en el enunciado:** "usando la ley de Ampere determine", "solenoide largo con $n$ vueltas por unidad de longitud", "cable coaxial con densidades de corriente simétricas".
    

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Naturaleza Vectorial y el Signo de la Carga ($q$):** Al usar la regla de la mano derecha (dedos en la dirección de $\vec{v}$, se curvan hacia $\vec{B}$, el pulgar indica la fuerza $\vec{F}_B$), el resultado es estrictamente válido para cargas **positivas**. Si la partícula en el examen es un electrón o un ion negativo, la fuerza real tendrá exactamente la misma dirección pero el **sentido opuesto** (pulgar invertido). No olvidar este cambio de sentido en el plano cartesiano.
    
- **Ángulo en la Fuerza Magnética vs. Ángulo en el Flujo:** * En las fórmulas de fuerza ($F_B = qvB\sin\phi$ o $F_B = ILB\sin\phi$), $\phi$ representa el ángulo directo entre los vectores conductores o de movimiento y las líneas de campo. Si son perpendiculares, $\sin(90^\circ)=1$ (máxima fuerza).
    
    - En la fórmula de flujo ($\Phi_B = BA\cos\theta$), el ángulo $\theta$ se mide respecto al **vector normal de la superficie**. Si el campo es paralelo a la superficie del anillo o espira, la normal queda a $90^\circ$, haciendo que el flujo sea cero ($\cos(90^\circ) = 0$).
        
- **Fuerza Magnética y Trabajo:** Un campo magnético estático **nunca realiza trabajo** sobre una partícula cargada aislada porque la fuerza es siempre perpendicular a la velocidad en todo instante ($\vec{F}_B \cdot \vec{v} = 0$). Por lo tanto, un campo magnético puede cambiar la dirección del vector velocidad (desviar la partícula), pero jamás alterará su rapidez ni su energía cinética. Si un problema de examen pregunta por el cambio de rapidez debido a un campo magnético puro, la respuesta es siempre cero.
    
- **Conversión de Unidades de Masa y Distancia:** Las masas de las partículas subatómicas suelen requerir el uso de constantes estándar en kilogramos (ej. masa del electrón $\approx 9.11 \times 10^{-31}\text{ kg}$, protón $\approx 1.67 \times 10^{-27}\text{ kg}$). Las distancias dadas en centímetros o milímetros deben convertirse inmediatamente a metros para evitar errores de órdenes de magnitud al operar con $\mu_0$.
    

---
## Paso a Paso de Resolución

Para resolver problemas sobre fuerzas magnéticas y fuentes de campo de forma estructurada, siga este algoritmo:

1. **Determinar la Naturaleza del Problema:** Clasifique el ejercicio en uno de los siguientes tipos esenciales:
    
    - Interacción sobre una carga en movimiento (cinemática de partículas).
        
    - Interacción sobre un alambre conductor con corriente.
        
    - Cálculo de un campo magnético creado por corrientes (Biot-Savart o Ampere).
        
2. **Establecer el Sistema de Coordenadas y Extraer Datos vectoriales:** Dibuje los ejes cartesianos ($x, y, z$). Anote los vectores de datos provistos en forma de componentes o determine sus direcciones espaciales relativas empleando la notación estándar para vectores entrantes ($\otimes$) o salientes ($\odot$) del plano del papel.
    
3. **Calcular la Magnitud del Efecto:** * Si es el movimiento circular de una carga, iguale la fuerza magnética a la fuerza centrípeta ($|q|vB = \frac{mv^2}{r}$) para despejar la incógnita de interés (como el radio o la masa).
    
    - Si es el cálculo de campo de un alambre, verifique si la longitud es infinita para aplicar directamente las ecuaciones integradas simplificadas (como $B = \frac{\mu_0 I}{2\pi r}$).
        
4. **Determinar la Dirección y el Sentido mediante Reglas de la Mano Derecha:**
    
    - **Para Fuerzas:** Oriente la mano derecha extendida en dirección a la velocidad $\vec{v}$ (o corriente $I$), cierre los dedos hacia el campo $\vec{B}$, y determine el sentido del pulgar. Invierta el sentido si la carga es negativa.
        
    - **Para Fuentes:** Apunte el pulgar de la mano derecha en la dirección de la corriente eléctrica que fluye por el alambre; el giro natural de los cuatro dedos restantes indicará de manera exacta la dirección concéntrica de las líneas de campo magnético generadas a su alrededor.
        
5. **Efectuar la Suma Vectorial (Principio de Superposición):** Si existen múltiples fuentes de campo o cables paralelos, calcule las magnitudes de campo de forma independiente en el punto de estudio, determine sus vectores unitarios correspondientes y realice la suma algebraica por componentes independientes ($B_{x,\text{total}} = \sum B_x$, etc.) para obtener el campo neto resultante.