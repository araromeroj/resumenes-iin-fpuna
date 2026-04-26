# Ventanas Corredizas

## Fórmulas de Velocidad y Tiempo

1. **Velocidad de Propagación ($V_p$):**
    
    - **En el vacío/aire:** $V_p = c \approx 3 \times 10^8$ m/s o $300,000$ km/s.
        
    - **En medios físicos (Fibra/Cobre):** $V_p = \frac{c}{n}$ (Donde $n$ es el índice de refracción).
        
    - _Tip:_ Si no dan $n$, usa $V_p = 2 \times 10^8$ m/s ($2/3$ de $c$).
    
2. **Tiempo de Propagación:** $T_p = d / V_p$ (Retraso por distancia).
    
3. **Tiempo de Transmisión:** $T_t = L / R$ (Retraso por "empujar" los bits al cable).

## Eficiencia ($\eta$) y Pipelining

La eficiencia mide qué tan bien usamos el ancho de banda.

- **Parada y Espera ($W=1$):** $\eta = \frac{T_t}{T_t + 2T_p + T_{ack}}$
    
- **Ventana Deslizante (General):** $\eta = \frac{W \cdot T_t}{T_t + 2T_p + T_{ack}}$
    
- **Con Superposición (Piggybacking):**  $\eta = \frac{W \cdot T_t}{2T_t + 2T_p}$.

## Tipos de Ventana Corrediza
- **Stop and Wait:**
	- Ventana: $W=1$
		
	- Receptor: Envía un ACK al emisor cuando recibe una trama correctamente.
		
	- Error: Reenvía según temporizador
	
- **Go-Back-N (GBN):**
    
    - Ventana: $\text{MAX SEQ}=W = 2^k - 1$ (donde $k$ son los bits de secuencia).
        
    - Receptor: Solo 1 buffer. Si llega la trama $X+1$ antes que la $X$, la descarta. Solo acepta tramas recibidas en **orden**.
        
    - Error: El emisor reenvía **toda** la ventana a partir del error con un timer.
    
- **Repetición Selectiva (RS):**
    
    - Ventana: $W = 2^{k-1}$.
        
    - Receptor: Tiene buffer. Almacena tramas correctas aunque lleguen desordenadas.
        
    - Error: El emisor reenvía **solo** la trama dañada (más eficiente ante errores de ráfaga).

---

# Detección de errores
## CRC - Códigos de redundancia cíclica
Se basa en el tratamiento de cadenas de bits como representaciones de polinomios con coeficientes únicamente $0$ y $1$.
### Análisis del polinomio generador

- Detectar errores simples (1 bit): $G(x)$ debe tener más de un término $\neq0$ 
- Errores dobles (2 bits): se debe dividir un polinomio $x^t+1$ desde $t=2$ hasta $t=n-1$.
- Errores impares: debe contener al polinomio $(x+1)$ como factor.

>[!important] Un buen polinomio generador
>- Debe tener al menos 2 términos
>- El coeficiente de $x^0$ debe ser $1$.
>- No debe dividir $(x^t+1)$, para $2<t<n-1$
>- Debe tener el factor $(x+1)$

