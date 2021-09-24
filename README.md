# Clustering de palabras

Clasificacion de palabras en base al algoritmo k-means

Trabajo para la cátedra "Minería de Datos para Texto" de Laura Alonso Alemany - FaMAF 2021.

## Instalacion

- Clonar este repositorio
- Correr `pip3 install spacy sklearn numpy pandas matplotlib nltk`
- Ejecutar el notebook en el entorno de preferencia (conda, Visual Studio o jupyter notebook)

## Procedimiento

- Análisis morfosintáctico y funcionalidad de cada palabra
- Eliminación de oraciones con menos de 10 palabras
- Lematización de cada palabra restante
- Eliminacion de las stopwords
- Conteo de ocurrencias totales de cada lematizacion
- Creación de diccionario de palabras
  - Solo nos quedamos con las palabras number-like o las que su lematizacion aparezca mas de 60 veces (es decir las mas comunes)
  - Nos guardamos para cada palabra su POS (part-of-speech), su tag (part-of-speech mas detallado), y su DEP (syntactic dependency)
  - Ademas aplicamos triplas de dependencias con las palabras anteriores y posteriores (solo si la palabra acompañante aparece mas de 30 veces, o es num-like)
- Vectorización de las palabras
- Normalización de la matriz (número de ocurrencias totales de la columna sobre ocurrencias por cada fila)
- Elección de número de clusters (en este caso 50 o 100)
- Algoritmo k-means usando la distancia coseno

```
clusterPresidente = [word for word in key_words if clusters[key_words[word]] == clusters[key_words["presidente"]]]
print(clusterPresidente)


['joven', 'chica', 'jefe', 'presidente', 'funcionario', 'dirigente', 'ministro', 'titular', 'encuesta', 'especialista', 'líder', 'dueño', 'secretario', 'abogado', 'delegado', 'investigador', 'conductor', 'fiscal', 'vecino', 'inspector', 'monto']
```

```
clusterNoche = [word for word in key_words if clusters[key_words[word]] == clusters[key_words["noche"]]]
print(clusterNoche)

['noche', 'viernes', 'lunes', 'marzo', 'junio', 'noviembre']
```

```
clusterViaje = [word for word in key_words if clusters[key_words[word]] == clusters[key_words["viaje"]]]
print(clusterViaje)

['pareja', 'educación', 'acción', 'calidad', 'canal', 'acceso', 'grado', 'consulta', 'rechazo', 'valor', 'compromiso', 'viaje', 'bien', 'servicio', 'control', 'pobreza', 'obligación', 'libertad', 'par', 'confianza', 'conocimiento', 'cultura', 'homicidio', 'justicia', 'tarjeta', 'ayuda', 'gasto', 'voluntad', 'embargo']
```
