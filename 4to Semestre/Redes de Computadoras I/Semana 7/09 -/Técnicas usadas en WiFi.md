En las redes **WiFi** (**Wireless Fidelity** - Fidelidad Inalámbrica), estandarizadas por el **IEEE** (**Institute of Electrical and Electronics Engineers** - Instituto de Ingenieros Eléctricos y Electrónicos) bajo la norma **802.11**, se implementan diversas técnicas para enfrentar los desafíos de un medio compartido y ruidoso.

## 1. Técnicas de Confiabilidad

Debido a que el medio inalámbrico es inherentemente ruidoso y propenso a interferencias, se utilizan las siguientes estrategias para asegurar la entrega de datos:

- **Adaptación de Velocidad (**Rate Adaptation):** Consiste en disminuir la tasa de bits si la señal es débil. Las velocidades más bajas utilizan modulaciones más robustas que son más fáciles de recibir correctamente bajo condiciones adversas.
- **Fragmentación de tramas:** Enviar tramas más cortas aumenta la probabilidad de que lleguen sin errores en canales ruidosos, ya que una trama larga tiene mayor probabilidad de que alguno de sus bits se corrompa.
- **Acuses de Recibo (ACK - Acknowledgment):** Debido a que no se pueden detectar colisiones mientras se transmite (radio semidúplex), el receptor debe enviar siempre una trama de confirmación explícita tras recibir los datos correctamente. Si el emisor no recibe el **ACK**, asume que hubo un error y reintenta la transmisión.
- **Algoritmo de Retroceso (Backoff):** Si ocurre un error o colisión, el emisor duplica su periodo de espera aleatorio antes de volver a intentar el acceso al medio.

## 2. Técnicas de Ahorro de Energía

Dado que muchos dispositivos móviles dependen de baterías, el estándar **802.11** define mecanismos para evitar el desperdicio de energía:

- **Modo de Ahorro de Energía (PSM - Power Save Mode):** El dispositivo avisa al **AP** (**Access Point** - Punto de Acceso) que entrará en reposo ("dormitar"). El **AP** almacena las tramas destinadas a ese cliente y avisa de su presencia mediante un mapa de tráfico en las tramas de **Beacon** (**Baliza**) periódicas.
- **Entrega Automática de Ahorro de Energía (APSD - Automatic Power Save Delivery):** Introducido en **802.11e**, permite una gestión más eficiente donde el **AP** envía tramas al cliente inmediatamente después de que este le envía datos o durante periodos de servicio programados. Es ideal para aplicaciones como **VoIP** (**Voice over IP** - Voz sobre Protocolo de Internet).

## 3. Técnicas de Calidad de Servicio (QoS - Quality of Service)

Para priorizar tráfico crítico como voz o video frente a datos comunes, se utilizan estos mecanismos:

- **Espaciado Inter-trama de Arbitraje (AIFS - Arbitration Inter-Frame Space):** Se definen diferentes intervalos de espera (**IFS** - **InterFrame Spacing**) para cada tipo de trama. El tráfico de alta prioridad espera menos tiempo antes de intentar acceder al canal, ganando ventaja competitiva. (802.11e)
- **Oportunidad de Transmisión (TXOP - Transmission Opportunity):** Esta técnica otorga a una estación un tiempo fijo de emisión en lugar de permitirle enviar solo una trama. Esto resuelve la "anomalía de velocidad", evitando que estaciones lentas degraden el rendimiento de las estaciones más rápidas en el mismo espacio.
- **Función de Coordinación de Punto (PCF - Point Coordination Function):** Un modo de operación centralizado donde el **AP** realiza sondeos (**Polling**) a las estaciones para darles turno de transmisión de forma ordenada, aunque es menos común en la práctica que el modo distribuido.