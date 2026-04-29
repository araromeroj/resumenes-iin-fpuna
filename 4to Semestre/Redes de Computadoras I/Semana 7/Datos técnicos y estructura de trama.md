- **Preámbulo:** 56 bits alternando 1s y 0s.
- [*] **SFD - Start Frame Delimiter:** Delimitador de inicio de trama.

![[Pasted image 20260429101928.png]]

- **Tamaño mínimo de carga útil:** 46 bytes
- **Tamaño máximo de carga útil:** 1500 bytes
- **Tamaño mínimo de trama:** 521 bits = 64 bytes
- **Tamaño máximo de trama:** 12.144 bits = 1.518 bytes
![[Pasted image 20260429101951.png]]

## Campo Protocolo - Longitud de trama
El significado de este campo depende de la cantidad de bits que posee:
- Si es $>1536$: **Protocolo** de nivel de red al que pertenecen los datos. Ethertype.
- Si es $>1536$:  **Longitud** de los datos de la trama Ethernet.
Si el campo indica la longitud, el Ethertype está al principio de los datos, en una cabecera adicional "LLC/SNAP"

![[Pasted image 20260429102012.png]]

## Direcciones Ethernet MAC Address

- [I] **Unicast:** bit menos significativo del primer byte = 0
- [I] **Multicast:** bit menos significativo del primer byte = 1
- [I] **Broadcast:** $FF:FF:FF:FF:FF:FF$
	- Los tres primeros bytes: define el fabricante.
	- Los últimos tres bytes: números de serie.

![[Pasted image 20260429181456.png]]

---
# Enlaces relacionados
- [[Ethernet]]
- [[Evolución del Ethernet]]