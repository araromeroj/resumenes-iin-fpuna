# Modulación por Desplazamiento de Frecuencia (FSK)

La **Modulación por Desplazamiento de Frecuencia** (Frequency Shift Keying o **FSK**) es una técnica de modulación digital donde la información se transmite a través de variaciones en la **frecuencia** de una onda portadora.


![FSK_image](https://www.open.edu/openlearn/pluginfile.php/871656/mod_oucontent/oucontent/44735/596a8165/03661243/tm355_bk1_pt2_f019.eps.jpg)
## 1. Concepto Fundamental

En FSK, los valores binarios (0 y 1) se representan mediante dos frecuencias distintas alrededor de una frecuencia central.

- La amplitud y la fase de la portadora permanecen **constantes**.
    
- Solo cambia la **frecuencia**.
    

## 2. Funcionamiento Técnico

En la forma más básica, llamada **BFSK** (Binary FSK), se utilizan dos frecuencias:

- **Bit 1 (Mark):** Se transmite una frecuencia f1​ (generalmente más alta).
    
- **Bit 0 (Space):** Se transmite una frecuencia f0​ (generalmente más baja).
    

La señal modulada se puede describir matemáticamente como:

s(t)=Acos(2πfi​t)

Donde fi​ cambia entre f1​ y f0​ dependiendo del bit de datos entrante.

---

## 3. Características Principales

A diferencia de ASK, FSK es mucho más robusto frente a los problemas de transmisión:

- **Inmunidad al ruido:** Como el ruido suele afectar a la amplitud de la señal, FSK (que depende de la frecuencia) es mucho menos propenso a errores causados por interferencias atmosféricas o ruido eléctrico.
    
- **Consumo de potencia:** La potencia de la señal es constante ya que la amplitud no varía.
    

---

## 4. Ventajas y Desventajas

###  Ventajas

- **Resistencia al ruido:** Mayor fiabilidad en canales con muchas interferencias.
    
- **Simplicidad:** Sigue siendo relativamente fácil de implementar en comparación con técnicas más avanzadas como QAM.
    

###  Desventajas

- **Ancho de banda:** Requiere un mayor ancho de banda que ASK porque necesita "espacio" para operar en dos frecuencias diferentes y evitar que se solapen.
    
- **Complejidad del receptor:** El receptor debe ser capaz de detectar cambios de frecuencia, lo que lo hace ligeramente más complejo que un detector de envolvente simple de ASK.
    

---

## 5. Aplicaciones Comunes

- **Modems antiguos:** Los primeros modems telefónicos utilizaban FSK para transmitir datos.
    
- **Sistemas de Radio teletipo (RTTY):** Muy comunes en comunicaciones de radioaficionados.
    
- **Identificación de llamadas (Caller ID):** La información del número que llama se envía a menudo usando FSK.
    
- **Sistemas de Telemetría:** Transmisión de datos desde sensores remotos.
    

---