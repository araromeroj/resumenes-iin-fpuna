- [I] **Espectro expandido (o ensanchado):** Método de codificación importante para las comunicaciones inalámbricas.
Ver: [[2. Capa Física]]
## FHSS - Espectro ensanchado por Salto de Frecuencia

- [*] **FHSS - Frequency Hopping Spread Spectrum:** Espectro expandido por salto de frecuencia.

En el FHSS, la señal no se mantiene en una frecuencia fija, sino que el transmisor **salta de una frecuencia a otra e cientos de veces por segundo**.

>[!tip] Funcionamiento
> Los saltos siguen una **secuencia pseudoaleatoria** de frecuencias conocida tanto por el emisor como el receptor, quienes deben estar sincronizados.

==Es utilizada en canales militares (por ser difícil de interferir), en Bluetooth y en versiones antiguas de 802.11==
#### Slow FHSS
El tiempo entre saltos es de $T_c$ es mayor o igual a la duración del elemento de señal $T_s$.
$$T_c\geq{T_s}$$
![[Slow FHSS.png|500]]
#### Fast FHSS
El tiempo entre saltos es menor que la duración del elemento de señal, lo que ofrece un mayor rendimiento frente al ruido.
$$T_c<T_s$$
![[Fast FHSS.png|500]]
## DSSS - Espectro ensanchado de secuencia directa

- [*] **DSSS -  Direct Sequence Spread Spectrum:** Espectro ensanchado por secuencia directa.

Utiliza una secuencia de códigos para distribuir la señal de datos por una banda de frecuencias más amplia.

>[!tip] Funcionamiento
>Cada bit de datos se representa mediante múltiples bits denominados **chips**, utilizando un código de expansión o secuencia de dispersión.

==Es utilizada en la base de redes móviles 3G, del sistema GPS y de los estándares antiguos de WiFi como el 802.11b

# Ventajas del espectro expandido

1.  **Inmunidad al ruido e interferencias:** Al estar la señal repartida, las interferencias de banda estrecha solo afectan a una pequeña fracción de la transmisión, permitiendo recuperar los datos.
	
2. **Resistencia al desvanecimiento multitrayecto:** Minimiza los errores causados por los ecos de la señal que rebotan en objetos sólidos y llegan desfasados al receptor.
	
3. **Seguridad y confidencialidad:** Hace que las transmisiones sean muy difíciles de detectar, interceptar o "escuchar" para quienes no conocen la secuencia de saltos o el código de expansión.
	
4. **Uso compartido del medio:** Permite que múltiples usuarios compartan la misma banda de frecuencias simultáneamente con mínima interferencia entre ellos, asignando códigos diferentes a cada uno (base del **CDMA**).

# Enlaces Relacionados
- [[2. Capa Física]]
- [[Medios no guiados de transmisión]]
- [[Ultra Wideband Communication (UWB]]