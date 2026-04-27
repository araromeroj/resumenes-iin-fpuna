## Ejercicio 1: Comparativa de Eficiencia

>[!note] Ejercicio 1
>Una red utiliza un canal compartido de 56 kbps para transmitir tramas de 1000 bits.
>- **A)** Si se utiliza **ALOHA Puro**, ¿cuál es la máxima cantidad de tramas por segundo que la red puede transportar con éxito (throughput)?
>- **B)** ¿Cómo cambiaría este resultado si se implementara **ALOHA Ranurado**?
>- **C)** Explica brevemente por qué existe esa diferencia de rendimiento entre ambos.

### Solución del Ejercicio 1

**Datos:**
- Velocidad ($R$): 56 kbps (56,000 bps). 
- Tamaño de trama ($L$): 1000 bits.
- Tiempo de trama ($T$): $L / R = 1000 / 56,000 \approx 0.01785$ segundos (17.85 ms).

**A) ALOHA Puro:** La eficiencia máxima de ALOHA Puro es del **18.4%** ($1/2e$).

- **Cálculo:** $Throughput = 0.184 \times (56,000 \text{ bps} / 1000 \text{ bits/trama}) = 0.184 \times 56 = 10.3$ tramas/seg.
- **Argumento:** En ALOHA puro, cualquier transmisión que comience durante el tiempo de vulnerabilidad (que es de $2T$) causará una colisión. Por ello, su capacidad es muy limitada.

**B) ALOHA Ranurado:** La eficiencia máxima de ALOHA Ranurado es del **36.8%** ($1/e$).

- **Cálculo:** $Throughput = 0.368 \times 56 = 20.6$ tramas/seg.
- **Argumento:** Al obligar a las estaciones a transmitir solo al inicio de una ranura de tiempo, el tiempo de vulnerabilidad se reduce de $2T$ a $1T$, duplicando exactamente la capacidad del canal.

**C) Explicación de la diferencia:** La diferencia radica en la **sincronización**. En ALOHA Puro, una trama puede colisionar con cualquier otra que haya empezado antes o empiece después. En el Ranurado, una trama solo colisiona con las que intentan enviarse en su misma ranura exacta, reduciendo el riesgo de "solapamiento parcial" entre tramas.

---
## Ejercicio 2: Probabilidad de Colisión

>[!note] Ejercicio 2
>Supongamos que un sistema de **ALOHA Puro** genera 0.5 tramas por cada tiempo de trama (G=0.5).
>- **A)** ¿Cuál es la probabilidad de que una trama se transmita con éxito en su primer intento? (Recuerda la fórmula P0​=e−2G).
>- **B)** Si el sistema fuera **ALOHA Ranurado** con la misma carga (G=0.5), ¿cuál sería la probabilidad de éxito?
### Solución del Ejercicio 2

**A) ALOHA Puro con $G = 0.5$:**

- **Fórmula:** $P_{éxito} = e^{-2G}$
- **Cálculo:** $P = e^{-2(0.5)} = e^{-1} \approx 0.367$ (36.7%).
- **Argumento:** $G$ representa el número promedio de tramas generadas por tiempo de trama. La probabilidad de éxito es la probabilidad de que **cero** tramas adicionales se generen en el intervalo de vulnerabilidad de $2T$. Según la distribución de Poisson, eso es $e^{-2G}$.

**B) ALOHA Ranurado con $G = 0.5$:**

- **Fórmula:** $P_{éxito} = e^{-G}$
- **Cálculo:** $P = e^{-0.5} \approx 0.606$ (60.6%).
- **Argumento:** Como el tiempo de vulnerabilidad es solo $1T$, solo necesitamos que no se generen otras tramas en ese único intervalo. Por eso la probabilidad de éxito es significativamente mayor bajo la misma carga de tráfico.

---
## Ejercicio 3: Análisis de Tráfico (Carga Crítica)

>[!note] Ejercicio 3
>En el libro de Tanenbaum se explica que la carga del canal (G) incluye tanto las tramas nuevas como las retransmisiones por colisiones.
>- **Escenario:** Tienes una red ALOHA Ranurado donde el número de estaciones aumenta drásticamente, haciendo que la carga G pase de 1.0 a 2.0.
>- **Pregunta:** ¿Qué sucede con la eficiencia (S) del canal en este caso? ¿El canal se vuelve más eficiente, se mantiene igual o entra en colapso? Justifica tu respuesta basándote en la curva de rendimiento de ALOHA.
### Solución del Ejercicio 3

**Escenario:** Red ALOHA Ranurado donde $G$ sube de $1.0$ a $2.0$.

**Análisis:**
1. **En $G = 1.0$:** La eficiencia del ALOHA Ranurado ($S = G \times e^{-G}$) alcanza su punto máximo teórico: $1 \times e^{-1} = 0.368$.
2. **En $G = 2.0$:** Si calculamos la eficiencia, $S = 2 \times e^{-2} \approx 2 \times 0.135 = 0.270$.

**Respuesta y Argumento:** La eficiencia **disminuye**.
- **Argumento técnico:** Según la curva de rendimiento que aparece en las diapositivas y en Tanenbaum, el protocolo ALOHA es intrínsecamente inestable. Una vez que la carga $G$ supera el valor crítico (que es $1.0$ para el ranurado), el número de colisiones aumenta de forma exponencial.
- **Consecuencia:** Más colisiones implican más retransmisiones, lo que aumenta aún más $G$, creando un círculo vicioso que reduce el número de tramas entregadas con éxito ($S$) y aumenta el retardo. En términos de redes, decimos que el canal se está congestionando y se dirige hacia el **colapso por saturación**.

---
# Enlaces relacionados
- [[Protocolos de Acceso Múltiple]]