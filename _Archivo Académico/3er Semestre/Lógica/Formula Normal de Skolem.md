El proceso de pasar a la Forma Normal de Skolem se centra en la sintaxis de la fórmula, pero su validez se basa en la **semántica** (interpretaciones).

---

## 1. Variables Libres y Ligadas 🔗

En una fórmula de lógica de primer orden, las variables pueden ser **libres** o **ligadas** (cuantificadas).

- **Variable Ligada:** Es una variable que está dentro del alcance de un cuantificador ($\forall$ o $\exists$).
    
    - **Ejemplo:** En $\forall x P(x, y)$, la variable $x$ está ligada por $\forall x$.
        
- **Variable Libre:** Es una variable que no está ligada por ningún cuantificador. Estas variables actúan como "parámetros" que pueden ser sustituidos por elementos específicos del dominio.
    
    - **Ejemplo:** En $\forall x P(x, y)$, la variable $y$ es **libre**.
        

Especificación (o Cierre Existencial):

Antes de aplicar la FNS, si una fórmula contiene variables libres (como y en el ejemplo anterior), a menudo se realiza el cierre existencial de la fórmula. Esto consiste en anteponer un cuantificador existencial para cada variable libre, convirtiéndolas en variables ligadas. Esto es crucial porque la Skolemización se aplica típicamente a fórmulas cerradas (sin variables libres).

$$\text{Fórmula con variables libres } F(y) \rightarrow \text{Cierre Existencial } \exists y F(y)$$

---

## 2. Interpretación Verdadera (Modelo) ✅

Una **interpretación** ($I$) para una fórmula $F$ es una estructura que define el significado de todos los símbolos (constantes, funciones y predicados) en el dominio de discurso.

Una interpretación es **verdadera** si la fórmula $F$ resulta ser cierta (valor de verdad "Verdadero") bajo esa interpretación. A esto se le llama **Modelo**.

- **Definición de Interpretación ($I$):**
    
    1. Define un **Dominio** ($D$), un conjunto no vacío de objetos.
        
    2. Asigna a cada **constante** un elemento de $D$.
        
    3. Asigna a cada **símbolo de función** una función del dominio $D$ a sí mismo.
        
    4. Asigna a cada **símbolo de predicado** un subconjunto del dominio $D$ (que representa los conjuntos o relaciones que el predicado es verdadero para).
        
- **Ejemplo de Interpretación Verdadera:**
    
    - **Fórmula:** $\exists x \text{Par}(x)$
        
    - **Interpretación $I$ (Modelo):**
        
        - **Dominio $D$:** El conjunto de los números enteros ($\mathbb{Z}$).
            
        - **Predicado $\text{Par}(x)$:** Significa " $x$ es divisible por 2".
            
        - **Verdadero/Falso:** La fórmula es **verdadera** bajo esta interpretación porque existe al menos un número entero que es par (ej: 4). $I \models \exists x \text{Par}(x)$.
            

---

## 3. Interpretación Falsa (Contramodelo) ❌

Una interpretación es **falsa** si la fórmula $F$ resulta ser falsa (valor de verdad "Falso") bajo esa interpretación. A esto se le llama **Contramodelo**.

- **Ejemplo de Interpretación Falsa:**
    
    - **Fórmula:** $\exists x \text{Par}(x)$
        
    - **Interpretación $I$ (Contramodelo):**
        
        - **Dominio $D$:** El conjunto de $\{1, 3, 5\}$ (números impares).
            
        - **Predicado $\text{Par}(x)$:** Significa " $x$ es divisible por 2".
            
        - **Verdadero/Falso:** La fórmula es **falsa** bajo esta interpretación porque en el dominio $\{1, 3, 5\}$ no existe ningún elemento que satisfaga el predicado "Par". $I \not\models \exists x \text{Par}(x)$.
            

---

## 4. Pasar a la Forma Normal de Skolem (FNS)

La FNS es un proceso **sintáctico** (cambia la estructura de la fórmula) motivado por consideraciones **semánticas** (satisfacibilidad).

El paso clave es la **Skolemización**, que elimina los cuantificadores existenciales y los reemplaza por **símbolos de función nuevos** (funciones o constantes de Skolem).

|**Paso**|**Explicación**|**Finalidad Semántica**|
|---|---|---|
|**1. FNP**|Convertir la fórmula a Forma Normal Prenexa (todos los cuantificadores al inicio).|Poner todos los cuantificadores en orden para determinar de cuáles dependen los existenciales.|
|**2. Skolemización**|Eliminar cada $\exists x$ y reemplazar $x$ por:|**Preservar la Equisatisfacibilidad:** Si la fórmula original era satisfacible, la FNS también lo será.|
||**a) Constante $c$** si no hay $\forall$ precedentes.|Esto asume la existencia de **algún** elemento que hace la fórmula verdadera.|
||**b) Función $f(y_1, \dots, y_n)$** si está precedida por $\forall y_1, \dots, \forall y_n$.|Esto formaliza el axioma de elección: si para cada $y$ existe un $x$, entonces hay una _función_ $f$ que "elige" ese $x$ en función de $y$.|

**Resultado Semántico Final:** La Fórmula Normal de Skolem ($F_{sko}$) **no es lógicamente equivalente** a la original ($F$), pero es **equisatisfacible**.

$$F \text{ es satisfacible } \iff F_{sko} \text{ es satisfacible}$$

Esto es suficiente para los métodos de prueba automatizada como la **Resolución**, que solo requieren saber si una fórmula es satisfacible o no.