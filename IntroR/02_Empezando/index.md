Empezando con R
========================================================
author: 
date: 
autosize: true

1. R como calculadora

2. Dónde guardar datos en R - vectores y otros objetos

3. Importar datos a R

1.
=========================
type: sub-section
<br><br>
# R Como calculadora

1.1 R como una calculadora
========================================================


```r
1 + 1
```

```
[1] 2
```

```r
10 - 5
```

```
[1] 5
```

```r
10 / 2
```

```
[1] 5
```
***

```r
2^3  # potenciación
```

```
[1] 8
```

```r
2 * 5  # sin o con espacios
```

```
[1] 10
```

```r
2*5
```

```
[1] 10
```
<small>Espacios pueden facilitar la lectura</small>

1.2 R como calculadora
========================================================


```r
10 %% 5 # módulo (resto de la división entera)
```

```
[1] 0
```

```r
10 %% 6
```

```
[1] 4
```
1.3 R como calculadora
========================================================

```r
10 %/% 5 # división entera (resultado de la división sin fracción)
```

```
[1] 2
```

```r
10 %/% 6
```

```
[1] 1
```

```r
18 %% 12 # p. ej convertir de 24h a 12h
```

```
[1] 6
```

1.4 R como calculadora
============================

Para ayuda con los operadores:
`? Arithmetic`

O con la función:
`help(Arithmetic)`

Ojo con el orden de los operadores...

- `^`
- `%%  %/%`
- `*  /`
- `+  -`

Ver 
`? Syntax`


1.5 R como calculadora
===============================


```r
10 + 10 / 2 - 1
```

```
[1] 14
```

```r
(10 + 10) /2 - 1
```

```
[1] 9
```

```r
8 - 4 * 4 + 2 
```

```
[1] -6
```

En RStudio puedes seleccionar una parte del código en el script y ejecutarlo con ctrl + enter

1.6 R como calculadora
===============================

Si no te acuerdas del orden, o tienes dudas, usa parentesis....

```r
10 + (10 / 2) - 1
```

```
[1] 14
```

```r
10 + 10 / 2 - 1
```

```
[1] 14
```

1.7 R como calculadora
===============
type: prompt
<br>
# Práctica

2.
======================
type: sub-section
<br><br>
# Vectores, variables y otros objetos

2.1 ¿Qúe es un vector?
=========================


### Colección ordenada de datos  
<br>

```
[1] 0.80 0.79 0.91 0.64 0.79 0.28 0.21 0.60
```
Por ejemplo, filas o columnas de datos  
<br>

```
[1] 3.142
```
O un solo valor

2.2 Tipos de vector
=================
<br>
- Numérico (numeric)
 - variable continuo
 - variable entero

- Carácter (character, string)
 - texto

- Lógico (logical)
TRUE o FALSE

2.3 Vector con un solo dato numérico
========================


```r
a <- 1
b <- 5
x <- 100
# Operador de asignación: <-
```

```r
a
```

```
[1] 1
```

```r
x
```

```
[1] 100
```
***
<small> **Para nombrar variables...**
- No usar palabras reservadas  
`? reserved`
- Mejor no usar nombres de funciones
- No empezar con número
- Sensible a mayúsculas/minúsculas
- No usar espacios
- No usar simbolos como £ $ % ^ & * ( ) # ? < > / | \ [ ] { }
</small>

2.4 Operaciones con vectores 1
======================


```r
a + b
```

```
[1] 6
```

```r
(a + b) * x
```

```
[1] 600
```

```r
a / x
```

```
[1] 0.01
```
***

```r
sum(a, b)
```

```
[1] 6
```

```r
sqrt(x)
```

```
[1] 10
```

```r
log10(x)
```

```
[1] 2
```

2.5 Vector de carácter
=======================


```r
a <- "Hola"  # texto entre "comillas"
b <- "Mundo"
sp1 <- "Phytotoma raimondii"
```

```r
a  # el nombre del objeto no tiene comillas
```

```
[1] "Hola"
```

```r
sp1
```

```
[1] "Phytotoma raimondii"
```

2.6 Operaciones con texto
=======================


```r
# Imprimir a la consola
print(a)
```

```
[1] "Hola"
```

```r
# concatenar texto
paste(a, b)
```

```
[1] "Hola Mundo"
```

```r
# con un separador
paste(a, sp1, sep=", ")
```

```
[1] "Hola, Phytotoma raimondii"
```

2.7 Vectores de varios elementos
========================


```r
1:10 # generar una serie de números
```

```
 [1]  1  2  3  4  5  6  7  8  9 10
```

```r
# Usar la función c() y asignar a un vector llamado v1
v1 <- c(1,2,3,4,5)
v2 <- 5:10
```

```r
v2
```

```
[1]  5  6  7  8  9 10
```
<small>Vectores solo admiten un tipo de dato (númerico, carácter, lógico)</small>

2.8 Operaciones con vectores 2
==================================


```r
v1 * 3  # cf. en excel
```

```
[1]  3  6  9 12 15
```

```r
v1 + v2
```

```
[1]  6  8 10 12 14 11
```

```r
mean(v1)
```

```
[1] 3
```

```r
sum(v1)/length(v1)
```

```
[1] 3
```

2.9 Acceder a un valor dentro de un vector con índices []
============================


```r
v1[3]  # acceder al 3r elemento de v1
```

```
[1] 3
```

```r
v1[2:4] # obtener elementos 2 a 4 de v1
```

```
[1] 2 3 4
```

```r
v1[-1] # obtener todos los elementos de v1 menos el primero
```

```
[1] 2 3 4 5
```

2.9 Series de letras
========================


```r
s1 <- c("a", "b", "c", "d", "e")
s2 <- letters[1:5]  # letters es un objeto en R
s3 <- LETTERS[1:5]  # ? Constants
```

```r
s2
```

```
[1] "a" "b" "c" "d" "e"
```

```r
s3
```

```
[1] "A" "B" "C" "D" "E"
```


2.10 Acceder a un elemento de un vector de caracteres
========================


```r
s1[1]
```

```
[1] "a"
```

```r
s1[4:5]
```

```
[1] "d" "e"
```

```r
sp1[1] # ¿Es lo que esperabas?
```

```
[1] "Phytotoma raimondii"
```

```r
s1[-2]
```

```
[1] "a" "c" "d" "e"
```

2.11 El Data frame - una "tabla" en R
==========================
Podemos pensar en el data frame como una colección de vectores del mismo largo


```r
v1
```

```
[1] 1 2 3 4 5
```

```r
s1
```

```
[1] "a" "b" "c" "d" "e"
```

```r
df1 <- data.frame(Tipo = s1, Valor = v1)
```

2.12 Data frame
==========================
  
- un objeto básico para almacenar datos  
  

```r
df1
```

```
  Tipo Valor
1    a     1
2    b     2
3    c     3
4    d     4
5    e     5
```
Más en la otra clase...  stay tuned!

2. Vectores
======================
type: prompt
<br>
# Práctica

3.
==================
type: sub-section
<br><br>
# Importar datos a R

3.1 Importar datos a R
========================
Directamente desde el teclado usando lo que ya vimos

`v1 <- c(...)`

- Lento
- Normalmente tenemos los datos en otro programa, como excel.
- Incluso, es más fácil ingresar datos en otro programa

3.2 Importar desde excel
=======================

Tenemos un ejemplo como este:
![Hoja de excel](images/SparrowFirst_Excel.bmp "Datos en excel")
***
![Bird measurements](images/634px-BirdMorphometrics.jpg)
<small>Die Vogel : Handbuch der Systematischen Ornithologie. Volume 1</small>

3.3 Preparar los datos en excel 1
======================
<small>
**Formato**
- Una variable por columna
- Una observación/ un caso/ sujeto, etc., por fila
- Primera columna - identificador de casos
- Primera fila - nombre (código) del variable - recuerda criterios para nombrar los vectores
- Es decir: 
 - Sin espacios
 - Sin palabras reservadas, nombres de funciones
 - No usar simbolos como: £ $ % ^ & * ( ) # ? < > / | \ [ ] { }
 - No muy largo (después tienes que escribir estos nombres)
</small>

3.4 Preparar los datos en excel 2
=====================
<small>
- Llenar con NA donde no hay datos
- Chequear los datos antes de importarlos (volvemos a este tema en un par de semanas)
- Ojo con caracteres especiales como # o " en campos de texto
- Borrar columnas y filas vacias aledañas a los datos (a veces quedan "restos" en filas y columnas que han tenido datos anteriormente)
- Guardar como texto (.txt o .csv)
</small>

3.5 Guardar como texto
========================

![Save as screen shot](images/Sparrow_SaveAs_ScrnSht.bmp)
***
![Text file screen shot](images/sparrowstext_Screenshot.png)

3.6 Importar con read.table()
=======================
<small>
Función básica para importar datos como un data frame

```r
df1 <- read.table("data/Sparrow_First.txt", sep="\t", header=TRUE,  dec = ".")
```
- OJO con la ruta. Usa `/` o `\\`.  Rutas en tu computador dependen del plataforma (Windows, Mac, etc)
 - p. ej. `"C:\data\Sparrow_First.txt"` en Windows tiene que cambiarse a 
`"C:/data/Sparrow_First.txt"` o `"C:\\data\\Sparrow_First.txt"`
- OJO con el delimitador de campos
 - `sep = "\t"` para tabs, (.txt) o `sep = ","` para coma (.csv)
- OJO con el character para puntos decimales
 - `dec = "."`  3.14  o `dec = ","`  3,14  
 
</small>

3.7 Siempre chequear lo que has importado 1
===========================

Dos funciones muy importantes!!

```r
head(df1)
```

```
  Especie   Sexo Culmen Peso Observador
1    SESP Female   15.2 22.8          2
2    SESP Female   15.0 21.7          2
3    SESP Female   14.9 21.1          3
4    SESP Female   14.8 20.9          8
5    SESP Female   14.4 19.7          3
6    SESP   Male   14.9 24.4          1
```

3.8 Siempre chequear lo que has importado 2
===========================

Dos funciones muy importantes!!

```r
str(df1)
```

```
'data.frame':	20 obs. of  5 variables:
 $ Especie   : Factor w/ 2 levels "SESP","SSTS": 1 1 1 1 1 1 1 1 1 1 ...
 $ Sexo      : Factor w/ 3 levels "Female","Male",..: 1 1 1 1 1 2 2 2 2 2 ...
 $ Culmen    : num  15.2 15 14.9 14.8 14.4 14.9 15.8 16 15.8 14.6 ...
 $ Peso      : num  22.8 21.7 21.1 20.9 19.7 24.4 22.8 22.6 25.2 NA ...
 $ Observador: int  2 2 3 8 3 1 1 1 2 2 ...
```

3.9 Importar desde el "clipboard"
===============================

Cuando copias texto o datos en el computador, lo que copias se almacena temporalmente en el "clipboard" hasta que lo pegues en otra aplicación o archivo

Puedes copiar una tabla en excel, y leerlo desde el clipboard en R


```r
df2 <- read.table("clipboard", sep="\t", header=TRUE,  dec = ".")
```
Argumento `sep` es siempre tab, `"\t"` para copiar desde excel

Solo apto para pocos datos, y no es reproducible, pero es una solución rápida.


3.10 Importar con file.choose()
=============================

Otro método rápido es buscar el archivo de manera interactiva.

Usar la función `file.choose()` dentro de `read.table()`


```r
df2 <- read.table(file.choose(), sep="\t", header=TRUE,  dec = ".")
```

Tienes que navegar hasta el archivo de texto.
Tampoco es reproducible.


3.11 Organización de tu código
=======================

Puedes escribir directamente en la consola, pero pierdes el código despues de cerrar el programa (aunque puedes grabar el historial de la consola)

- Es útil tener tu código guardado en un script
 - Si vuelves a utilizar pedacitos de código, los tienes a la mano
 - Para compartir lo que has hecho
 - Investigación reproducible
 - Volver a correr los mismo análisis

Guaradar en un archivo de texto, con la extensión .r

3.12 Organización de tu código
=================================

Archivo de código en RStudio
![Script in RStudio screenshot](images/RStudioScript.png)
****
El mismo archivo en notepad
![Script in notepad screenshot](images/NotepadScript.png)

3.13 Organización de los archivos
===========================
<small>
Crear una carpeta para tu trabajo, puede tener subcarpetas para datos (crudos, procesados), resultados, etc.

>Establecer la carpeta como el "working directory"  
>`setwd("C:/Documentos/CursoR/Trabajos")`  - ruta de la carpeta entre " "

Recuerda cambiar los \ en Windows

Todas la rutas que escribes ahora pueden iniciar en tu "working directory"  
> En vez de usar esta ruta  
> `"C:/Documentos/CursoR/Trabajos/Rscript.r"`  
> usas solamente `"Rscript.r"`

Para saber cual es tu "working directory" usar la función `getwd()`
</small>

3. Importar datos a R
======================
type: prompt
<br>
# Práctica
