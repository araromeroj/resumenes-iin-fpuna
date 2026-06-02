## Teoría de los PPT's de la Prof. Ruth Meaurio

La Unidad V, dividida en sus dos componentes síncronos y analizada a través de los documentos de la cátedra, abarca la unificación de los fenómenos eléctricos y magnéticos mediante variables temporales.

### 1. Fuerza Electromotriz Inducida y Ley de Faraday

Los experimentos fundamentales realizados en 1831 por Michael Faraday y Joseph Henry demostraron de forma concluyente que es posible introducir una fuerza electromotriz (fem) y, por consiguiente, una corriente eléctrica en un circuito utilizando exclusivamente un **campo magnético variable** con respecto al tiempo.

La base matemática de este fenómeno es la **Ley de Inducción de Faraday**, la cual sostiene que la magnitud de la fem inducida en un circuito es directamente proporcional a la rapidez de cambio temporal del flujo magnético ($\Phi_B$) que atraviesa la superficie delimitada por el circuito. Si se trata de una bobina compacta compuesta por un número $N$ de espiras idénticas, la expresión adopta la forma:

$$\varepsilon = -N \frac{d\Phi_B}{dt}$$

El flujo magnético se concibe como el producto escalar del vector campo magnético y el vector área. Al desglosar el diferencial, la variación del flujo puede ser provocada por tres mecanismos físicos distintos diferenciados en el material de la cátedra:

- Variación del módulo del campo magnético en el tiempo ($\frac{dB}{dt}$).
    
- Variación del área del circuito expuesta al campo ($\frac{dA}{dt}$).
    
- Variación de la orientación angular de la espira respecto a las líneas de campo mediante rotación ($\omega = \frac{d\theta}{dt}$).
    

### 2. Dirección de la fem Inducida: Ley de Lenz

El signo negativo incorporado en la Ley de Faraday representa la **Ley de Lenz**. Esta ley posee una fundamentación basada en el principio de conservación de la energía y determina que la dirección de una fem o corriente inducida es tal que el campo magnético secundario creado por dicha corriente tiende a **oponerse activamente al cambio** de flujo magnético original que la produjo.

El documento establece reglas claras de signos para su evaluación analítica:

1. Se define una dirección positiva para el vector de área $\vec{A}$.
    
2. A partir de la dirección de $\vec{A}$, se utiliza la regla de la mano derecha para establecer el sentido positivo para la fem y la corriente inducida a lo largo de la trayectoria.
    
3. Se determina el signo del cambio de flujo $\frac{d\Phi_B}{dt}$. Si el flujo aumenta, el cambio es positivo; si disminuye, es negativo.
    
4. El signo de la fem resultante de la ecuación matemática indicará si la corriente circula en el sentido positivo asignado o en sentido contrario.
    

### 3. Fuerza Electromotriz en Movimiento (fem de movimiento)

Un caso especial y de alta relevancia en los ejercicios es el de un conductor rectilíneo de longitud $l$ que se desplaza con una velocidad constante $v$ de forma perpendicular a un campo magnético uniforme $\vec{B}$.

Dentro del conductor en movimiento, las cargas libres experimentan una fuerza magnética de magnitud $F_m = qvB$. Esta fuerza desplaza los electrones hacia uno de los extremos del conductor, acumulando carga y estableciendo un campo eléctrico interno $\vec{E}$. El movimiento de carga cesa cuando se alcanza el equilibrio electrostático, es decir, cuando la fuerza eléctrica compensa exactamente a la fuerza magnética:

$$qE = qvB \implies E = vB$$

Dado que la diferencia de potencial o voltaje a lo largo del conductor de longitud $l$ está dada por $\Delta V = El$, se deduce la ecuación de la fem en movimiento:

$$\Delta V = B l v$$

Si este conductor móvil forma parte de un circuito cerrado (como una barra deslizándose sobre rieles paralelos fijos sin fricción separados una distancia $l$ y conectados a una resistencia $R$), el área del circuito varía en función de la posición $x$ del conductor ($\Phi_B = Blx$). Al aplicar la ley de Faraday, se demuestra que la magnitud de la fem inducida en la trayectoria cerrada es idéntica: $|\varepsilon| = Blv$. La corriente inducida en la espira será $I = \frac{\varepsilon}{R} = \frac{Blv}{R}$. Para mantener la barra moviéndose a velocidad constante, se debe ejercer una fuerza externa que iguale a la fuerza magnética ejercida sobre el conductor con corriente ($F_{\text{magnética}} = IlB$), disipándose energía en forma de potencia mecánica y eléctrica: $P = F_{\text{externa}}v = I^2R = \frac{B^2l^2v^2}{R}$.

### 4. Autoinductancia e Inductor

El fenómeno de **autoinductancia** ocurre cuando una corriente variable $I$ circula por un circuito, generando un campo magnético propio variable que interactúa con el propio circuito, induciendo una fem que se opone a la variación de la corriente original (fuerza contraelectromotriz).

La propiedad física que cuantifica este efecto es la inductancia o autoinductancia ($L$), definida matemáticamente como la razón entre el flujo magnético total ligado y la corriente que lo produce:

$$L = \frac{N\Phi_B}{I}$$

A partir de este parámetro intrínseco del dispositivo, la fem autoinducida se expresa en función del cambio de corriente como:

$$\varepsilon_L = -L \frac{dI}{dt}$$

La unidad de medida de la inductancia en el Sistema Internacional es el **Henry (H)**, donde $1\text{ H} = 1\text{ V}\cdot\text{s/A}$. Para un solenoide de longitud $l$ devanado uniformemente con $N$ vueltas y área transversal $A$, la inductancia es $L = \frac{\mu_0 N^2 A}{l}$.

### 5. Circuitos RL

Un circuito RL es una red en serie compuesta por una fuente de voltaje continuo $\mathcal{E}$, una resistencia de valor $R$ y un inductor de inductancia $L$. Al cerrar el interruptor, el inductor genera una fem opuesta al crecimiento de la corriente. Aplicando la Ley de las Mallas de Kirchhoff en el sentido de las manecillas del reloj, se plantea la ecuación:

$$\mathcal{E} - V_R - V_L = 0 \implies \mathcal{E} - IR - L\frac{dI}{dt} = 0$$

La solución de esta ecuación diferencial para el crecimiento de la corriente con una condición inicial $I(0) = 0$ es:

$$I(t) = \frac{\mathcal{E}}{R} \left(1 - e^{-\frac{R}{L}t}\right)$$

La constante de tiempo del circuito RL se define como $\tau = \frac{L}{R}$. Representa el tiempo requerido para que la corriente alcance el $63.2\%$ de su valor máximo asintótico de equilibrio ($I_{\text{máx}} = \frac{\mathcal{E}}{R}$).

### 6. Energía Almacenada por el Campo Magnético

Un inductor no consume energía de forma irreversible, sino que la acumula temporalmente en el espacio donde se establece su campo magnético. Multiplicando la ecuación de malla por la corriente instantánea, se obtiene la tasa de transferencia de energía. Integrando dicha expresión, la energía total almacenada ($U_B$) por un inductor cuando transporta una corriente estable $I$ se calcula como:

$$U_B = \frac{1}{2} L I^2$$

---
## Guía de Fórmulas y Aplicación

### 1. Ley de Faraday Completa

- **Ecuación:** $\varepsilon = -N \frac{d\Phi_B}{dt}$
    
- **Variables y Unidades:**
    
    - $\varepsilon$: Fuerza electromotriz inducida [Voltios, $\text{V}$].
        
    - $N$: Número de vueltas o espiras compactas de la bobina [Adimensional].
        
    - $\Phi_B$: Flujo magnético individual por espira [Webers, $\text{Wb}$].
        
    - $t$: Variable tiempo [Segundos, $\text{s}$].
        
- **Identificadores en el enunciado:** "Bobina con N vueltas experimenta una variación de flujo", "calcular la fem media inducida en un intervalo de tiempo", "campo magnético cambia a razón constante".
    

### 2. Fuerza Electromotriz de Movimiento Lineal

- **Ecuación:** $\varepsilon = B l v$
    
- **Variables y Unidades:**
    
    - $B$: Magnitud del campo magnético uniforme [Teslas, $\text{T}$].
        
    - $l$: Longitud del segmento de barra conductora recta [Metros, $\text{m}$].
        
    - $v$: Rapidez de traslación del conductor perpendicular al campo [Metros por segundo, $\text{m/s}$].
        
- **Identificadores en el enunciado:** "Una barra de longitud l se desliza sobre rieles paralelos", "conductor se mueve perpendicularmente a un campo magnético uniforme", "determinar la diferencia de potencial entre los extremos del ala de un avión en vuelo".
    

### 3. Parámetros Eléctricos de una Barra en Rieles Cerrados

- **Ecuaciones:** $I = \frac{Blv}{R}$ ; $F_{\text{ext}} = I l B = \frac{B^2l^2v}{R}$ ; $P = \frac{B^2l^2v^2}{R}$
    
- **Variables y Unidades:**
    
    - $I$: Intensidad de la corriente inducida en la espira rectangular [Amperios, $\text{A}$].
        
    - $R$: Resistencia eléctrica total de la malla [Ohmios, $\Omega$].
        
    - $F_{\text{ext}}$: Fuerza mecánica requerida para mantener la rapidez constante [Newtons, $\text{N}$].
        
    - $P$: Potencia mecánica o tasa de disipación térmica Joule [Vatios, $\text{W}$].
        
- **Identificadores en el enunciado:** "Barra se mueve sin fricción sobre rieles conectados a una resistencia R", "calcular la fuerza necesaria para mantener la barra a velocidad v", "hallar la potencia disipada por efecto Joule".
    

### 4. Autoinductancia

- **Ecuación:** $L = \frac{N\Phi_B}{I} = \frac{\mu_0 N^2 A}{l}$
    
- **Variables y Unidades:**
    
    - $L$: Inductancia o autoinductancia del componente [Henrios, $\text{H}$].
        
    - $\mu_0$: Permeabilidad magnética del vacío ($4\pi \times 10^{-7}\ \text{T}\cdot\text{m/A}$).
        
    - $A$: Área de la sección transversal del solenoide [$\text{m}^2$].
        
    - $l$: Longitud longitudinal del devanado del solenoide [Metros, $\text{m}$].
        
- **Identificadores en el enunciado:** "Encontrar la inductancia de un solenoide largo", "solenoide devanado uniformemente con núcleo de aire", "calcular el flujo magnético si circula una corriente conocida".
    

### 5. Fuerza Electromotriz Autoinducida

- **Ecuación:** $\varepsilon_L = -L \frac{dI}{dt}$
    
- **Variables y Unidades:**
    
    - $\varepsilon_L$: Fuerza electromotriz autoinducida [Voltios, $\text{V}$].
        
    - $\frac{dI}{dt}$: Tasa instantánea de variación de la corriente eléctrica [Amperios por segundo, $\text{A/s}$].
        
- **Identificadores en el enunciado:** "La corriente en el inductor disminuye a razón de...", "calcular la fem autoinducida en una bobina cuando se abre el interruptor".
    

### 6. Corriente de Carga en Circuito RL

- **Ecuación:** $I(t) = \frac{\mathcal{E}}{R} \left(1 - e^{-\frac{R}{L}t}\right)$
    
- **Variables y Unidades:**
    
    - $I(t)$: Corriente instantánea en el tiempo $t$ [Amperios, $\text{A}$].
        
    - $\mathcal{E}$: Voltaje continuo de la fuente de alimentación [Voltios, $\text{V}$].
        
    - $\tau = \frac{L}{R}$: Constante de tiempo del circuito transitorio [Segundos, $\text{s}$].
        
- **Identificadores en el enunciado:** "Se cierra el interruptor de un circuito RL en serie", "determinar la corriente después de un tiempo t", "calcular el tiempo para que la corriente alcance la mitad de su valor máximo".
    

### 7. Energía en el Campo Magnético

- **Ecuación:** $U_B = \frac{1}{2} L I^2$
    
- **Variables y Unidades:**
    
    - $U_B$: Energía potencial magnética acumulada Julios, $\text{J}$.
        
    - $I$: Corriente instantánea o de régimen permanente que circula por las espiras Amperios, $\text{A}$.
        
- **Identificadores en el enunciado:** "Calcule la energía almacenada por el campo magnético del inductor", "determinar la energía cuando el circuito alcanza el estado estable".
    

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Signo de la Razón de Cambio de Corriente ($\frac{dI}{dt}$):** Cuando el enunciado indica que "la corriente disminuye a razón de $50\text{ A/s}$", matemáticamente implica que $\frac{dI}{dt} = -50\text{ A/s}$. Al sustituir en la ecuación de fem autoinducida $\varepsilon_L = -L \frac{dI}{dt}$, el doble signo negativo resulta en una fem con signo algebraico positivo, actuando a favor de mantener la corriente. Omitir el signo del decrecimiento es un error penalizado en los exámenes de la Politécnica.
    
- **Geometría y Conversión de Unidades:** Las áreas transversales de los solenoides suelen expresarse en centímetros cuadrados ($\text{cm}^2$). Debe convertirlas a metros cuadrados multiplicando por $10^{-4}\ \text{m}^2/\text{cm}^2$. Del mismo modo, la longitud del solenoide dada en centímetros ($\text{cm}$) debe dividirse entre $100$ para llevarla a metros. Las inductancias se presentan comúnmente en milihenrios ($\text{mH} = 10^{-3}\text{ H}$).
    
- **Comportamiento del Inductor en Tiempos Límite:** * En el instante instantáneo de cierre del interruptor ($t = 0$), la corriente es idénticamente **cero** ($I = 0$), el inductor produce una fem que cancela a la fuente y se comporta como un **circuito abierto**.
    
    - Tras transcurrir un tiempo muy largo ($t \to \infty$ o estado estable), la corriente deja de variar ($\frac{dI}{dt} = 0$). Por lo tanto, la fem del inductor es **cero** ($\varepsilon_L = 0$) y se comporta físicamente como un **cortocircuito** (un cable conductor ideal con resistencia nula).
        
- **El Vector Normal y el Flujo:** Al evaluar espiras rotativas o planos inclinados, recuerde siempre que el flujo magnético involucra el coseno del ángulo formado entre el vector de campo $\vec{B}$ y el **vector normal** al plano de la espira, nunca respecto a la superficie de la chapa conductora directamente.
    

---
## Paso a Paso de Resolución

Para resolver sistemáticamente problemas complejos de inducción electromagnética y circuitos RL, aplique el siguiente algoritmo analítico:

1. **Determinar la Naturaleza de la Variación:** Analice el problema para identificar qué elemento genera el fenómeno de inducción. Clasifíquelo en:
    
    - Inducción por movimiento mecánico (barra deslizante).
        
    - Inducción por variación temporal de una fuente externa (Faraday puro).
        
    - Fenómeno de autoinducción en un inductor estable o transitorio RL.
        
2. **Establecer Geometría y Parámetros del Solenoide/Circuito:** Si el problema involucra un inductor físico, calcule primero su inductancia propia empleando las variables de construcción ($N, A, l$) mediante la fórmula $L = \frac{\mu_0 N^2 A}{l}$. Asegúrese de unificar todas las unidades al Sistema Internacional.
    
3. **Plantear el Diferencial o Tasa Temporal:** * Si el campo cambia de forma lineal, calcule $\frac{\Delta B}{\Delta t} = \frac{B_f - B_i}{t_f - t_i}$.
    
    - Si la corriente cambia, extraiga directamente el dato de variación $\frac{dI}{dt}$ cuidando el signo algebraico (positivo si crece, negativo si decrece).
        
4. **Calcular Magnitudes de fems:** Sustituya los valores numéricos en la ley correspondiente:
    
    - $\varepsilon = -N \frac{d\Phi_B}{dt}$ para bobinas.
        
    - $\varepsilon_L = -L \frac{dI}{dt}$ para bornes de un inductor.
        
    - $\varepsilon = Blv$ para conductores móviles.
        
5. **Aplicar la Ley de Lenz para Sentidos de Corriente:** Realice un diagrama del circuito. Dibuje el sentido del campo original. Si el flujo aumenta, determine que el campo inducido debe apuntar en sentido opuesto; si disminuye, debe apuntar en el mismo sentido. Use la regla de la mano derecha envolviendo el circuito con los dedos para deducir si la corriente circula en sentido horario o antihorario.
    
6. **Resolver la Cinemática o el Transitorio Temporal (si aplica):** * Para problemas de barras móviles, iguale las ecuaciones de potencia disipada o fuerzas según corresponda.
    
    - Para problemas de circuitos RL, use la función exponencial $I(t) = \frac{\mathcal{E}}{R} (1 - e^{-t/\tau})$. Si requiere aislar el tiempo $t$, aísle el término exponencial y aplique logaritmos naturales ($\ln$) en ambos miembros del desarrollo algebraico.