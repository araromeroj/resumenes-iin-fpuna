## 1. El primer filtro: ¿Qué tipo de variable tienes?

- **Cualitativas vs. Cuantitativas:** En los modelos de probabilidad, casi siempre trabajamos con variables **cuantitativas** (números). Si tu problema habla de variables cualitativas (ej. "cara" o "cruz", "semáforo en verde" o "rojo", "pieza defectuosa" o "sana"), lo que hacemos es _cuantificarlas_ asignándoles un valor numérico (generalmente 1 para "éxito" y 0 para "fracaso"). A esto le llamamos **Variable Aleatoria**.
- **Discretas vs. Continuas:** Esta es la distinción más importante.
    - **Discreta:** Se **cuenta** en números enteros. (Ej: número de autos, cantidad de semáforos, tiros de un dado). Saltan de un valor a otro (1, 2, 3...).
    - **Continua:** Se **mide** y puede tomar cualquier valor dentro de un intervalo, incluyendo decimales infinitos. (Ej: el tiempo que esperas un autobús, el peso de una persona, la distancia exacta).

---

## 2. Guía para Variables Aleatorias Discretas (Contar)

Si determinaste que tu variable es discreta, pregúntate: **¿Qué estoy contando exactamente?**

- **¿Cuentas el número de éxitos en un número FIJO de intentos?**
	
    - _Características:_ Tienes $n$ intentos definidos, solo hay dos resultados posibles (éxito/fracaso), y la probabilidad de éxito $p$ siempre es la misma (hay reemplazo).
    - _Fórmula:_ **Distribución Binomial**. (Ej: Tiras 10 monedas, ¿cuál es la probabilidad de sacar 3 caras?).
    
- **¿Cuentas la cantidad de intentos necesarios hasta conseguir el PRIMER éxito?**
    
    - _Características:_ Solo hay dos resultados posibles, la probabilidad $p$ es constante, pero no sabes cuántos intentos harás. Te detienes en el primer éxito.
    - _Fórmula:_ **Distribución Geométrica**. (Ej: ¿Cuántas veces debo tirar un dado hasta que me salga un 6?).
    
- **¿Cuentas la cantidad de intentos necesarios hasta lograr un NÚMERO ESPECÍFICO de éxitos ($k$)?**
    
    - _Características:_ Igual que la geométrica, pero en lugar de parar en el primer éxito, paras en el segundo, tercero, décimo, etc.
    - _Fórmula:_ **Distribución Binomial Negativa (o de Pascal)**. (Ej: El inciso "a" de tu ejercicio anterior).
    
- **¿Cuentas eventos que ocurren en un intervalo fijo de TIEMPO o ESPACIO?**
    
    - _Características:_ Tienes una tasa promedio de ocurrencia (llamada $\lambda$). No cuentas "intentos", sino cuántas veces pasa algo en una hora, en un metro cuadrado, en una página web.
    - _Fórmula:_ **Distribución de Poisson**. (Ej: ¿Cuántos clientes llegan a una caja registradora en 15 minutos?).
        
- **¿Cuentas éxitos en una muestra pequeña extraída SIN REEMPLAZO?**
    
    - _Características:_ Es como la Binomial, pero al no devolver el elemento sacado, la probabilidad $p$ cambia en cada intento.
    - _Fórmula:_ **Distribución Hipergeométrica**. (Ej: De una caja con 5 bolas rojas y 5 azules, saco 3 al mismo tiempo. ¿Cuál es la probabilidad de que 2 sean rojas?).

---

## 3. Guía para Variables Aleatorias Continuas (Medir)

Si tu variable es continua, las preguntas cambian. Aquí ya no usas sumatorias, sino integrales (o tablas ya calculadas):

- **¿Los datos se agrupan alrededor de un valor central formando una campana simétrica?**
    
    - _Características:_ Conoces la media ($\mu$) y la desviación estándar ($\sigma$). Es la más común en la naturaleza.
        
    - _Fórmula:_ **Distribución Normal (o de Gauss)**. (Ej: La estatura de los estudiantes de una universidad, errores de medición).
        
- **¿El tiempo que transcurre ENTRE dos eventos de Poisson?**
    
    - _Características:_ Mide el tiempo de espera continuo hasta que ocurra un evento.
        
    - _Fórmula:_ **Distribución Exponencial**. (Ej: El tiempo exacto que tarda en fallar un componente electrónico).
        
- **¿Todos los valores en un intervalo tienen exactamente la misma probabilidad de ocurrir?**
    
    - _Características:_ Forma un rectángulo plano en un gráfico.
        
    - _Fórmula:_ **Distribución Uniforme Continua**. (Ej: Un tren llega en algún momento aleatorio y uniforme entre las 10:00 y las 10:30).

---
