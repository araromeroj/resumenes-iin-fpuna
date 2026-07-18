## Síntesis Teórica Detallada

La Unidad III analiza el comportamiento de las cargas eléctricas cuando se encuentran en movimiento ordenado a través de materiales conductores, constituyendo los circuitos de corriente continua.

### 1. Corriente Eléctrica e Intensidad de Corriente ($I$)

Una corriente eléctrica consiste en todo movimiento de carga de una región del espacio a otra. Para que se establezca una corriente en un conductor, es indispensable mantener un campo eléctrico dentro de él mediante una diferencia de potencial externa.

- **Dirección convencional de la corriente:** Históricamente se definió que la corriente fluye en la dirección del movimiento de los portadores de carga positiva. En los conductores metálicos reales, los portadores de carga son electrones (negativos) y se desplazan en sentido contrario al campo eléctrico y al sentido convencional de la corriente.
    
- **Intensidad de corriente ($I$):** Es la cantidad neta de carga $dQ$ que pasa a través de una sección transversal del conductor por unidad de tiempo $dt$. Se mide en **Amperios (A)**, donde $1\text{ A} = 1\text{ C/s}$.
    
- **Velocidad de deriva o arrastre ($v_d$):** Aunque los electrones libres se mueven al azar a altas velocidades debido a la agitación térmica, en presencia de un campo eléctrico adquieren adicionalmente un movimiento lento y neto de avance denominado velocidad de deriva o arrastre en dirección opuesta al campo.
    

### 2. Densidad de Corriente ($\vec{J}$)

La densidad de corriente es una magnitud vectorial que describe el flujo de carga por unidad de área en cada punto del conductor. Su magnitud se define como la intensidad de corriente por unidad de área transversal ($J = I/A$). El vector $\vec{J}$ apunta siempre en la dirección del campo eléctrico, coincidiendo con el sentido convencional de la corriente.

### 3. Resistencia ($R$), Resistividad ($\rho$) y Ley de Ohm

- **Conductividad ($\sigma$) y Resistividad ($\rho$):** En ciertos materiales (especialmente los metales), la densidad de corriente es directamente proporcional al campo eléctrico establecido, relación que se expresa mediante la forma microscópica de la Ley de Ohm: $\vec{J} = \sigma \vec{E}$. La constante de proporcionalidad $\sigma$ es la conductividad del material, y su recíproco es la resistividad ($\rho = 1/\sigma$), que mide la oposición intrínseca del material al paso de la corriente.
    
- **Resistencia Eléctrica ($R$):** Es la propiedad de un componente de circuito específico que cuantifica su oposición al flujo de la corriente eléctrica. Para un conductor homogéneo de sección transversal uniforme $A$ y longitud $L$, la resistencia depende tanto del material como de su geometría:
    
    $$R = \rho \frac{L}{A}$$
    
    La unidad de medida de la resistencia en el Sistema Internacional es el **Ohmio ($\Omega$)**. La Ley de Ohm a nivel macroscópico relaciona la diferencia de potencial $V$ aplicada en los extremos del conductor con la corriente resultante: $V = I R$.
    

### 4. Dependencia de la Resistividad con la Temperatura

La resistividad de un conductor metálico varía de forma aproximadamente lineal con la temperatura en intervalos moderados. Al aumentar la temperatura, los átomos del metal vibran con mayor amplitud, incrementando la frecuencia de colisiones de los electrones de conducción y, por ende, elevando la resistividad. Se describe mediante:

$$\rho(T) = \rho_0 [1 + \alpha(T - T_0)]$$

Donde $\alpha$ es el coeficiente térmico de resistividad del material.

### 5. Fuerza Electromotriz (fem) y Resistencia Interna

Para mantener una corriente eléctrica continua en un circuito cerrado, se requiere un dispositivo (fuente de fem) capaz de realizar trabajo sobre las cargas para elevar su energía potencial eléctrica al moverlas del potencial bajo al alto.

- **Fuente ideal:** Mantiene una diferencia de potencial constante (voltaje de las terminales) idéntica a su fem ($\mathcal{E}$) independientemente de la corriente.
    
- **Fuente real con resistencia interna ($r$):** Los materiales propios de la fuente generan una resistencia interna al paso de la carga. Cuando circula una corriente $I$ por la fuente, el voltaje real disponible entre sus terminales ($V_{ab}$) cae debido a la pérdida interna de potencial: $V_{ab} = \mathcal{E} - I r$.
    

### 6. Potencia Eléctrica ($P$)

Cuando una corriente pasa a través de un elemento de circuito, se transfiere energía eléctrica al dispositivo. La rapidez de transferencia de energía por unidad de tiempo es la potencia:

$$P = V I$$

En un elemento puramente resistivo, toda la energía eléctrica entregada se disipa irreversiblemente en forma de calor por efecto Joule, lo que permite reescribir la potencia como $P = I^2 R = \frac{V^2}{R}$.

### 7. Leyes de Kirchhoff

Para circuitos complejos que no pueden reducirse mediante combinaciones simples en serie o paralelo, se aplican las dos leyes fundamentales de Kirchhoff, basadas en principios de conservación:

- **Ley de los Nudos (Conservación de la Carga):** La suma algebraica de las corrientes que entran a cualquier nudo (punto de unión de tres o más conductores) debe ser igual a la suma de las corrientes que salen de él: $\sum I_{\text{entra}} = \sum I_{\text{sale}}$.
    
- **Ley de las Mallas (Conservación de la Energía):** La suma algebraica de las diferencias de potencial en un recorrido cerrado alrededor de cualquier malla del circuito debe ser igual a cero: $\sum \Delta V = 0$.
    

### 8. Circuitos RC (Carga y Descarga de un Capacitor)

En los circuitos que contienen tanto resistores como capacitores, la corriente y la carga no son constantes, sino que varían en función del tiempo de manera exponencial.

- **Proceso de Carga:** Al cerrar el interruptor para conectar una fuente de fem $\mathcal{E}$ en serie con una resistencia $R$ y un capacitor inicialmente descargado $C$, la carga en las placas se incrementa gradualmente según la función: $q(t) = C\mathcal{E}(1 - e^{-t/RC})$. La corriente inicial es máxima ($I_0 = \mathcal{E}/R$) y decae exponencialmente hasta cero a medida que el capacitor se satura.
    
- **Proceso de Descarga:** Al desconectar la fuente y permitir que el capacitor cargado se descargue a través de la resistencia, la carga acumulada fluye hacia afuera disipándose en el resistor: $q(t) = Q_0 e^{-t/RC}$.
    
- **Constante de Tiempo ($\tau$):** El producto $\tau = RC$ define la constante de tiempo del circuito y representa el tiempo requerido para que la carga del capacitor alcance el $63.2\%$ de su valor máximo durante la carga, o para que decaiga hasta el $36.8\%$ de su valor inicial durante la descarga.
    

---
## Guía de Fórmulas y Aplicación

### 1. Intensidad de Corriente y Velocidad de Deriva

- **Ecuación:** $I = \frac{dQ}{dt} = n |q| v_d A$
    
- **Variables y Unidades:**
    
    - $I$: Intensidad de corriente [Amperios, $\text{A}$].
        
    - $Q$: Carga eléctrica neta [Culombios, $\text{C}$].
        
    - $n$: Densidad de portadores de carga libres por unidad de volumen [$\text{electrones/m}^3$].
        
    - $q$: Carga de cada portador de corriente ($1.6 \times 10^{-19}\text{ C}$ para electrones).
        
    - $v_d$: Velocidad de deriva o arrastre [$\text{m/s}$].
        
    - $A$: Área de la sección transversal del conductor [$\text{m}^2$].
        
- **Identificadores en el enunciado:** "calcular la velocidad de deriva de los electrones", "determinar cuánta carga fluye por segundo", "calibre de un alambre conductor con densidad de electrones".
    

### 2. Densidad de Corriente

- **Ecuación:** $J = \frac{I}{A} = n |q| v_d$
    
- **Variables y Unidades:**
    
    - $J$: Magnitud de la densidad de corriente [$\text{A/m}^2$].
        
    - Las demás variables conservan las mismas unidades descritas en la fórmula anterior.
        
- **Identificadores en el enunciado:** "calcule la densidad de corriente en un conductor cilíndrico", "alambre uniforme que transporta una corriente fija".
    

### 3. Resistencia Geométrica de un Conductor

- **Ecuación:** $R = \rho \frac{L}{A}$
    
- **Variables y Unidades:**
    
    - $R$: Resistencia eléctrica [Ohmios, $\Omega$].
        
    - $\rho$: Resistividad del material [Ohmios-metro, $\Omega \cdot \text{m}$].
        
    - $L$: Longitud del hilo o cable conductor [Metros, $\text{m}$].
        
    - $A$: Área transversal expuesta del alambre ($\pi r^2$ si es cilíndrico) [$\text{m}^2$].
        
- **Identificadores en el enunciado:** "un alambre de cobre de longitud L y diámetro D", "determinar la resistencia de una barra cilíndrica de grafito".
    

### 4. Voltaje de Terminales en una Fuente Real

- **Ecuación:** $V_{ab} = \mathcal{E} - I r$
    
- **Variables y Unidades:**
    
    - $V_{ab}$: Diferencia de potencial real entre las terminales de la fuente [Voltios, $\text{V}$].
        
    - $\mathcal{E}$: Fuerza electromotriz nominal (fem) de la batería [Voltios, $\text{V}$].
        
    - $I$: Corriente total que circula a través de la fuente [Amperios, $\text{A}$].
        
    - $r$: Resistencia interna de la batería [Ohmios, $\Omega$].
        
- **Identificadores en el enunciado:** "una batería con resistencia interna", "calcular el voltaje en los bornes de la fuente", "caída de voltaje interna".
    

### 5. Potencia Eléctrica Disipada

- **Ecuación:** $P = V I = I^2 R = \frac{V^2}{R}$
    
- **Variables y Unidades:**
    
    - $P$: Potencia disipada o consumida [Vatios o Watts, $\text{W}$].
        
    - $V$: Caída de tensión o diferencia de potencial en el resistor [Voltios, $\text{V}$].
        
    - $I$: Corriente eléctrica circulante [Amperios, $\text{A}$].
        
    - $R$: Valor de la resistencia [Ohmios, $\Omega$].
        
- **Identificadores en el enunciado:** "rapidez de generación de energía térmica", "potencia disipada por el resistor", "potencia nominal de una bombilla".
    

### 6. Ecuaciones Temporales en Circuitos RC (Carga)

- **Ecuación:** $q(t) = C\mathcal{E}(1 - e^{-t/RC})$ y $i(t) = \frac{\mathcal{E}}{R} e^{-t/RC}$
    
- **Variables y Unidades:**
    
    - $q(t)$: Carga instantánea acumulada en las placas en el tiempo $t$ [Culombios, $\text{C}$].
        
    - $i(t)$: Corriente instantánea en el circuito en el tiempo $t$ [Amperios, $\text{A}$].
        
    - $C$: Capacitancia del condensador [Faradios, $\text{F}$].
        
    - $\mathcal{E}$: Voltaje de la fuente de alimentación [Voltios, $\text{V}$].
        
    - $R$: Resistencia total en serie del circuito [Ohmios, $\Omega$].
        
    - $t$: Tiempo transcurrido desde el cierre del circuito [Segundos, $\text{s}$].
        
- **Identificadores en el enunciado:** "un circuito en serie consta de una resistencia y un capacitor inicialmente descargado", "determinar la corriente después de $t$ segundos de cerrar el interruptor", "fracción de la carga final".
    

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Conversión del Diámetro o Radio al Área:** El diámetro del alambre conductor se proporciona comúnmente en milímetros ($\text{mm}$). Es imperativo transformarlo a metros dividiendo entre $1000$ antes de calcular el área transversal. Recuerde que el área de una sección circular es $A = \pi r^2 = \pi \frac{D^2}{4}$, evite usar el diámetro directamente en el lugar del radio.
    
- **Convención de Signos en Mallas de Kirchhoff (Crucial):** Al recorrer una malla para plantear la ley de voltajes de Kirchhoff:
    
    - Al pasar a través de un **resistor** en la misma dirección que la corriente asignada, el cambio de potencial es **negativo** ($-IR$). Si se recorre en sentido opuesto a la corriente, el cambio es **positivo** ($+IR$).
        
    - Al pasar a través de una **fuente de fem** del terminal negativo al positivo (raya corta a raya larga), el cambio es **positivo** ($+\mathcal{E}$), sin importar la dirección de la corriente. Si se cruza del terminal positivo al negativo, el cambio es **negativo** ($-\mathcal{E}$).
        
- **Comportamiento del Condensador en Circuitos de Corriente Continua en Estado Estacionario:** Si el enunciado menciona que "el circuito lleva cerrado un tiempo muy largo" u "opera en estado estable", el capacitor se comporta físicamente como un **circuito abierto** (resistencia infinita). La corriente a través de la rama del capacitor en ese estado es estrictamente cero ($I = 0$).
    
- **Unidades de la Constante de Tiempo:** La constante de tiempo $\tau = RC$ requiere que la resistencia esté en Ohmios ($\Omega$) y la capacitancia en Faradios ($\text{F}$) para que el resultado resulte directamente en segundos ($\text{s}$). Convierta siempre microfaradios ($\mu\text{F}$) multiplicando por $10^{-6}$.
    

---
## Paso a Paso de Resolución

Para resolver de manera estructurada redes complejas mediante las leyes de Kirchhoff, emplee el siguiente algoritmo:

1. **Esquematizar el Circuito e Identificar Elementos:** Dibuje detalladamente el diagrama de conexiones. Identifique y marque todos los nudos (puntos donde convergen tres o más conductores) y cuente el número de mallas internas independientes.
    
2. **Asignar Corrientes en las Ramas:** Elija de manera arbitraria una dirección para la corriente en cada rama independiente del circuito (por ejemplo, $I_1, I_2, I_3$). Marque estas corrientes con flechas claras en su diagrama. Si al finalizar el desarrollo matemático una corriente resulta con valor negativo, significa simplemente que circula en sentido contrario al supuesto originalmente.
    
3. **Aplicar la Ley de los Nudos:** Escriba las ecuaciones de conservación para los nudos. Si el circuito posee $n$ nudos, plantee exactamente $n-1$ ecuaciones independientes de nudos para evitar redundancia algebraica.
    
4. **Definir Sentidos de Recorrido para las Mallas:** Seleccione una dirección de recorrido cerrado (horario o antihorario) de forma independiente para cada una de las mallas seleccionadas.
    
5. **Aplicar la Ley de las Mallas (Ecuaciones de Voltaje):** Recorra cada malla en el sentido definido en el paso anterior. Siga estrictamente la convención de signos descrita en el apartado de detalles clave al pasar por resistores, resistencias internas y fems. Iguale la suma algebraica total de voltajes de cada recorrido cerrado a cero ($\sum \Delta V = 0$).
    
6. **Resolver el Sistema de Ecuaciones Lineales:** Reúna las ecuaciones obtenidas de nudos y mallas. Deberá contar con un número de ecuaciones linealmente independientes exactamente igual al número de corrientes incógnitas planteadas en el paso 2. Resuelva el sistema mediante el método de su preferencia (sustitución, igualación o determinantes).
    
7. **Calcular Parámetros de Potencia y Energía:** Con las corrientes verdaderas ya determinadas, calcule si se solicita la potencia disipada en las resistencias ($P = I^2R$) o el voltaje real entregado por los bornes de las fuentes de energía ($V = \mathcal{E} - Ir$).
