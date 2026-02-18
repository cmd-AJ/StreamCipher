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
- El bytes (antes era arreglo pero se junto para un solo byte)


## Funcion de a generar el keystream
``` python
import random

def generar_keystream(seed: str, longitud: int) -> bytes:
    # Passing the current time as the seed value

    # En base a la libreriad e random (se utiliza una semilla para que genere el mismo cifrado.) que sea deterministico
    random.seed(seed)

    # Se crea un arreglo de bytes para poder almacenar. Es el mismo de list pero osea no consumis tanto espacio 
    arreglodebytes = bytearray()
    for _ in range(longitud):
        numero = random.randint(0, 255)  #Se elige de 8 bytes o pues 256 bits los número 
        arreglodebytes.append(numero)

    # regrsa el arreglo a bytes
    return bytes(arreglodebytes)
    

```

La función inicializa el PRNG con una semilla proporcionada por el
usuario y genera una secuencia de bytes pseudoaleatorios del tamaño
indicado.


-   La implementación completa del generador de keystream.
-   Pruebas de determinismo (misma semilla → mismo keystream).
-   Ejemplos de generación de keystream con distintas claves.
-   Implementación básica de cifrado y descifrado utilizando operación
    XOR.
-   Pruebas donde se demuestra el correcto funcionamiento del cifrado al
    usar la misma clave.
-   Ejemplos donde se evidencia que cambiar la clave produce un
    resultado diferente.

Este notebook sirve como demostración práctica del funcionamiento de un
Stream Cipher básico con fines académicos.

------------------------------------------------------------------------

## Nota Importante y esta deberia de estar en entorno de produccion:

La librería `random` de Python **no es criptográficamente segura**.\
Esta implementación es únicamente con fines educativos.\
En un entorno de producción real se debe utilizar un generador
criptográficamente seguro (CSPRNG), como `secrets`, `os.urandom`, o
algoritmos estandarizados como AES-CTR o ChaCha20.
