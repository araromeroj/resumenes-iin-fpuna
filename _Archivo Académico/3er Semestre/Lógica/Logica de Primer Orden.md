La Forma Normal de Skolem (FNS) es una representación de una fórmula en lógica de primer orden que solo contiene **cuantificadores universales** ($\forall$) en su prefijo. El proceso busca eliminar los existenciales ($\exists$) introduciendo **constantes** o **funciones de Skolem** para preservar la _satisfacibilidad_.

---

# 📜 Forma Normal de Skolem (FNS) - Pasos

## 1. Convertir a Forma Normal Prenexa (FNP)

El objetivo es mover todos los cuantificadores al inicio de la fórmula.

1. **Eliminar $\to$ y $\leftrightarrow$:**
    
    - Sustituir: $A \to B \equiv \neg A \lor B$
        
    - Sustituir: $A \leftrightarrow B \equiv (A \to B) \land (B \to A)$
        
2. **Reducir el Alcance de $\neg$:** Mover la negación hacia adentro (aplicar Leyes de De Morgan y equivalencias para cuantificadores).
    
    - $\neg (\exists x P(x)) \equiv \forall x (\neg P(x))$
        
    - $\neg (\forall x P(x)) \equiv \exists x (\neg P(x))$
        
3. **Renombrar Variables:** Asegurar que cada cuantificador use una variable única para evitar la **captura de variables**.
    
4. **Mover Cuantificadores al Inicio:** Extraer todos los cuantificadores al prefijo.
    
    - **Resultado (FNP):** Una fórmula en la forma $(Q_1 x_1)(Q_2 x_2) \dots (Q_n x_n) M$, donde $Q_i \in \{\forall, \exists\}$ y $M$ (la matriz) no contiene cuantificadores.
        

---

## 2. Skolemización (Eliminación de Cuantificadores Existenciales $\exists$)

Se eliminan los cuantificadores existenciales de izquierda a derecha.

### A. Si $\exists x$ no tiene $\forall$ precedentes:

Se sustituye la variable existencial por una **constante de Skolem** nueva.

|**Fórmula Original**|**Forma Skolemizada**|**Nota**|
|---|---|---|
|$\exists x P(x)$|$P(\mathbf{c})$|$\mathbf{c}$ es una nueva constante.|

### B. Si $\exists x$ está precedido por $\forall y_1, \dots, \forall y_n$:

Se sustituye la variable existencial por una **función de Skolem** nueva ($f$) que depende de las variables universales precedentes.

|**Fórmula Original**|**Forma Skolemizada**|**Nota**|
|---|---|---|
|$\forall y \exists x P(x, y)$|$\forall y P(\mathbf{f(y)}, y)$|$\mathbf{f}$ es una nueva función unaria.|
|$\forall y \forall z \exists x Q(x, y, z)$|$\forall y \forall z Q(\mathbf{g(y, z)}, y, z)$|$\mathbf{g}$ es una nueva función binaria.|

---

## 3. Forma Normal de Skolem Final

La fórmula resultante, después de eliminar todos los $\exists$, solo tendrá cuantificadores universales en el prefijo.

$$\color{green}{\Large (\forall y_1) (\forall y_2) \dots (\forall y_m)} \color{blue}{M'}$$

- $M'$ es la matriz (libre de cuantificadores) con las sustituciones de Skolem aplicadas.
    
- **Propiedad Clave:** La FNS es **equisatisfacible** con la fórmula original.
    

**(Paso Extra para Resolución):** Es común luego convertir la matriz $M'$ a **Forma Normal Conjuntiva (FNC)**, resultando en la **Forma Clausulada**.