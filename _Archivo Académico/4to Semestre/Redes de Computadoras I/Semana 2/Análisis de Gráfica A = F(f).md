(Gráfica de la Amplitud en función de la frecuencia) Para hallar el ancho de banda y el componente DC en una gráfica de amplitud respecto a la frecuencia (espectro de frecuencia), primero debemos entender qué estamos mirando: es una "foto" de cuánta energía tiene la señal en cada tono o frecuencia.

---
## ¿Qué es "DC" y cómo hallarlo?

**DC** significa _Direct Current_ (Corriente Continua). En términos de señales, representa el **valor promedio** de la señal en el tiempo o su componente constante.

- **En la gráfica:** El componente DC siempre se encuentra en la **frecuencia $0$ Hz**.
    
- **Cómo hallarlo:** Busca el eje vertical ($A$) justo cuando el eje horizontal ($f$) es cero. El valor de la amplitud en ese punto exacto es la magnitud de tu componente DC.


> **Dato curioso:** Si una señal es perfectamente simétrica respecto al cero en el tiempo (como un seno puro), su componente DC en la gráfica será **cero**.

---

## Cómo hallar el Ancho de Banda ($BW$)

El ancho de banda ($BW$) es el rango de frecuencias en el que la señal tiene "existencia" o potencia significativa. Se calcula restando la frecuencia más alta de la más baja.

$$BW = f_{max} - f_{min}$$

### El criterio de los -3 dB (Potencia a la mitad)

En gráficas reales, la señal no corta en seco, sino que se desvanece. Por convención, el ancho de banda se mide desde donde la amplitud es máxima hasta donde cae a un **70.7%** de ese valor máximo (que equivale a una caída de **3 dB** en potencia).

---

## Ejemplo Práctico

Imagina que tienes una gráfica de una señal de radio con los siguientes puntos:

- En $f = 0$ kHz, la amplitud es $2$V.
    
- La curva sube y baja, pero tiene valores significativos desde $f = 100$ kHz hasta $f = 120$ kHz.
    
- El pico máximo de amplitud está en $110$ kHz con $10$V.

### Extrayendo los datos:

1. **Hallar DC:** Miras el valor en $f = 0$. En este ejemplo, **DC = 2V**. Esto significa que la señal tiene un desplazamiento constante de 2 voltios hacia arriba.

2. **Hallar el Ancho de Banda:**
	- Identificas la frecuencia *más alta* con señal ($f_{max} = 120$ kHz).
		
    - Identificas la frecuencia *más baja* con señal ($f_{min} = 100$ kHz).
        
    - **Cálculo:** $120 \text{ kHz} - 100 \text{ kHz} = \mathbf{20 \text{ kHz}}$.        

---
### Resumen Visual

- **Punto en el origen ($0, A$):** Es el componente **DC**.
    
- **Ancho de la "montaña":** Es el **Ancho de Banda**.

---
## Enlaces relacionados
- [[2. Capa Física]]