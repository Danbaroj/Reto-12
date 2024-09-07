# Reto-12

1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper. 
- endswith

Determinasi una cadena de texto termina con los caracteres de una cadena indicada, devolviendo true o false según corresponda.
- startswith

Indica si una cadena de texto comienza con los caracteres de una cadena de texto concreta, devolviendo true o false según corresponda.
- isalpha

Devuelve True si todos los caracteres son alfabéticos, False de lo contrario.
- isalnum

Recibe el código ASCII de una carácter y devuelve el valor 1 si el carácter que corresponde a ese código ASCII es una letra o un dígito numérico; en caso contrario devuelve un 0.
- isdigit

Indica si el carácter que ocupa la posición especificada en una cadena especificada se clasifica por categorías como un dígito decimal.
- isspace

Se utiliza para comprobar el espacio en la cadena . Devuelve verdadero si solo hay caracteres de espacio en blanco en la cadena. De lo contrario, devuelve falso.
- istitle

Devuelve True si todas las palabras de un texto comienzan con una letra mayúscula Y el resto de la palabra son letras minúsculas; de lo contrario, devuelve False . Los símbolos y números se ignoran.
- islower

Devuelve True si todos los caracteres están en minúsculas, de lo contrario False . No se comprueban los números, símbolos ni espacios, solo los caracteres del alfabeto.
- isupper

Toma una cadena y devuelve True si todas las letras de la cadena están en mayúsculas; de lo contrario, devuelve False . Este método ignora espacios, nuevas líneas, caracteres numéricos y especiales en la cadena.

2. Procesar el archivo y extraer:

Cantidad de vocales

Cantidad de consonantes

Listado de las 50 palabras que más se repiten

```python
# Función para contar vocales
def contar_vocales(texto):
    vocales = 'aeiou'
    contador_vocales = 0
    for caracter in texto:
        if caracter in vocales:
            contador_vocales += 1
    return contador_vocales

# Función para contar consonantes
def contar_consonantes(texto):
    consonantes = 'bcdfghjklmnpqrstvwxyz'
    contador_consonantes = 0
    for caracter in texto:
        if caracter in consonantes:
            contador_consonantes += 1
    return contador_consonantes

# Función para obtener las 50 palabras más repetidas
def palabras_mas_repetidas(texto):
    # Eliminar caracteres que no son letras o espacios
    texto_limpio = ""
    for caracter in texto:
        if caracter.isalpha() or caracter.isspace():
            texto_limpio += caracter

    # Convertir el texto en una lista de palabras
    palabras = texto_limpio.split()

    # Contar la frecuencia de cada palabra
    frecuencias = {}
    for palabra in palabras:
        if palabra in frecuencias:
            frecuencias[palabra] += 1
        else:
            frecuencias[palabra] = 1

    # Ordenar palabras por frecuencia
    palabras_ordenadas = sorted(frecuencias.items(), key=lambda x: x[1], reverse=True)

    # Retornar las 50 palabras más repetidas
    return palabras_ordenadas[:50]

# --- IMPORTANTE ---
# cambiar la ruta del archivo al lugar donde se guardo  'mbox.txt'.
# Por ejemplo: 'C:/Users/Usuario/Desktop/mbox.txt'

# Leer el archivo (ruta actual para este entorno)
with open('C:/Users/danro/Downloads/mbox.txt', 'r', encoding='utf-8') as file:
    texto = file.read().lower()

# Llamar a las funciones y mostrar resultados
vocales = contar_vocales(texto)
consonantes = contar_consonantes(texto)
top_50_palabras = palabras_mas_repetidas(texto)

print(f"Cantidad de vocales: {vocales}")
print(f"Cantidad de consonantes: {consonantes}")
print("Las 50 palabras más repetidas:")
for palabra, frecuencia in top_50_palabras:
    print(f"{palabra}: {frecuencia}")


```
