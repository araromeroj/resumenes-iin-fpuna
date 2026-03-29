- [I] **Distancia de hamming:** es la cantidad mínima de bits cambiados para pasar de una palabra codificada válida a otra cualquiera.
	Un código con distancia mínima de Hamming **d** puede detectar palabras codificadas (codewords) con hasta **s** bits con error, donde $d_{min}\gt{s}$

>[!info] Funcionamiento de control de errores
>- Toma un mensaje de longitud **m**
>- Le agrega **r** bits de redundancia
>- Se obtiene una **palabra codificada** de longitud **n** $$n=m+r$$

## Detección
