# StreamCipher


# Primera Parte Generación del Keystream (20 puntos)


En esta sección especificamente la 1.1 de este modulo se implementa un Generador de Números Pseudoaleatorios
(PRNG) básico utilizando la librería `random` de Python.

En base a eso se tenia que cumplir los siguientes requisitos: 
- Utilice un generador de números pseudoaleatorios (PRNG) básico
- Acepte una clave (seed) como parámetro de inicialización
- Genere un keystream de longitud igual o mayor al mensaje a cifrar
- La función debe ser determinística: la misma clave debe producir el mismo keystream
------------------------------------------------------------------------

## Inputs 
-Longitud: del generador es de tipo integer y el tamaño del keystream generado es igual al valor de `longitud`.
-Semilla: Objeto a utilizar para generar la k es de tipo string


## Valor de Retorno
