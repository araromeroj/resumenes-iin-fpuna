---
tipo: Nota
materia: Redes de Computadoras I
fecha: 2026-03-09T14:00:00
semana: "2"
---
## Temas
- Tipos de canales según el sentido de transmisión
- Conceptos en el dominio del tiempo
- Análisis de Fourier
- Funciones en el dominio de la frecuencia
- Ancho de banda de la señal
- Ancho de banda del canal
- Señales de Audio
- Impedimentos de la transmisión de datos
- Máxima tasa de datos en un canal
- Fórmula de Nyquist
- Fórmula de Shannon
- Modulación Digital
	- Transmisión en banda base
- Aspectos en la codificación
- NRZ-L y NRZ-I
- Señales Balanceadas
- Bipolar o AMI y Pseudoternario
- Manchester (Bifase)
## Importante

El ancho de banda define la cantidad de Hz que puede transmitir un medio de transmisión.
- Atenuación: cuando se pierde la potencia de la señal debido a la distancia, de forma uniforme. (A mayor frecuencia, mayor atenuación) y se mide en **DECIBELES**.
- Distorsión por retraso y por atenuación: cuando varía la amplitud en las señales pero de forma desigual. Es la pérdida de la forma de la señal.
- Ruido

Retardo por propagación: depende de la distancia entre los puntos y de la velocidad de propagación ($\frac{m}{s}$)

### Fórmula de Nyquist
>[!warning] el profe se quedó mucho tiempo explicando esto.
>
>

Considera canales sin ruido.

Si se toma muestras de menos del doble del ancho de banda estamos **perdiendo** bits.
Si se toma muestras de más del doble del ancho de banda estamos midiendo **datos inservibles**.

>[!example] FÓRMULA DE NYQUIST
$$
C=2*B*log_2(M)
$$ 

- M: número de niveles o valores posibles para cada muestra o cantidad de muestras.
- C: máxima tasa de datos. 
- B: ancho de banda
- Tasa de muestreo puede ser como máximo el doble del ancho de banda.

### Fórmula de Shannon

SNR: Relación señal-ruido recibida.
$$\text{Máx tasa de datos} = B*log_2(1+SNR)\text{ [bits/segundo]}$$
---
### Modulación Digital

NRZ-L: si la señal es 0 entonces es ALTA, si la señal es 1 entonces es BAJA.
NRZI (No return to zero interted to ones): la señal debe invertirse si va a transmitir un bit 1. 

![[Comparacion NRZL y NRZI.png|500]]

Cosas a considerar
- Ancho de banda
- Componente "DC"
- Sincronismo
### Manchester (Bifase)
El cambio de bajo a alto se hace con el bit "1"
El cambio de alto a bajo se hace con el bot "0"
> Usado en IEEE 802.5

![[Manchester (bifase).png|500]]




___ 
# Tareas

- [<] Resumen pendiente
- [ ] Tarea pendiente
# Terminología

- [I] **Datos:** Entidades que contienen significado, o información. Pueden ser digitales (bits) o analógicos.
- [I] **Señales:** Representación eléctrica o electromagnética de los datos, se propagan físicamente a través de un medio.
- [I] **Transmisión de datos:** Entre un transmisor y un receptor vía un medio de transmisión, a través de la variación de propiedades de una señal en el tiempo.
- [I] **Espectro:** Rango de frecuencias contenidas en la señal, puede ser infinito.
- [I] **Ancho de Banda:** Es el rango de frecuencias de una señal entre las cuales se concentra la mayor parte de la energía de la señal.
- [I] **Señal analógica:** degradación de la calidad de señal.
- [I] **Señal digital:** errores de bits.
- [I] **Modulación digital:** La conversión de datos digitales (bits) a señales físicas.