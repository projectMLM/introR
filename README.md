# Comenzando

## ¿Qué es R?

Es un lenguaje de programación y entorno para la computación estadística y gráficos.

## ¿Por qué usar R para el análisis estadístico?

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\Ryears.png){width="50%"}

</center>

A.	Programa de fuente abierta:

-	Gratuito.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\stata.png){width="40%"}

</center>

-	Contribuciones que provienen alrededor de todo el mundo.

B. Cada vez el código de R es más accesible para público no especializado.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\oldcode.png){width="30%"}

</center>

C. Acceso a herramientas de análisis de datos altamente especializadas y actualizadas.

D. Automatiza tareas que demandan tiempo.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\tabla.png){width="80%"}

</center>

E. Competencia requerida en investigación.

F. Transparencia y reproductibilidad.

G. Permite hacer mucho más que análisis estadístico:

-	Escritura de libros, reportes y presentaciones.
-	Diseño de páginas web.
-	Programación de aplicaciones.

H. Existen múltiples recursos para aprender R de forma autodidacta.

## ¿Cómo descargar R?

R se puede descargar desde http://cran.r-project.org/bin/windows/base/. 

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\rdownload.png){width="120%"}

</center>

## R base

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN\r base.png){width="50%"}

</center>

Para facilitar el trabajo con R típicamente se utiliza un entorno de desarrollo integrado (*Integrated Development Environment*, IDE) denominado **Rstudio**.

## Rstudio

Descargar: 

https://posit.co/download/rstudio-desktop/

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\rstudiodownload.png){width="100%"}

</center>

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\interface.png){width="100%"}

</center>

## ¿Cómo funciona R?

La mayoría del trabajo con R abarca la aplicación de **funciones** sobre **objetos**.

### ¿Qué es un objeto?

Un **objeto** puede ser cualquier elemento que se ingresa y manipula dentro de R. 

Una secuencia de números del 1 al 10, los resultados de un modelo de regresión, o una base de datos con información de distintas personas en distintas variables se pueden considerar objetos en R.

Los objetos se definen la simbología **“<-”**, que se conoce como **operador de asignación**.

Por ejemplo, se puede asignar el resultado de sumar 2 + 2 a un objeto llamado suma.

```{r}
suma <- 2 + 2
```

El hecho de escribir nuevamente **suma** arrojará el contenido del objeto.

```{r}
suma
```

Los objetos también pueden ser elementos más complejos, como tablas, gráficos, o incluso modelos estadísticos.

El siguiente código asigna diferentes números a los objetos **a** y **b**, y luego asigna la correlación de Pearson entre ambos conjuntos de números a un nuevo objeto llamado **correlacion**.

```{r}
a <- c(1, 53, 69, 20, 67)
b <- c(2, 43, 89, 30, 50)

correlacion <- cor.test(x = a, y = b)
```

Escribir nuevamente el nombre del objeto **correlacion** devolverá la correlación de Pearson calculada con información adicional.

```{r}
correlacion
```

Los objetos también se pueden **actualizar**. Para agregar un nuevo número al objeto a simplemente se añade dentro de la secuencia (96).

```{r}
a <- c(1, 53, 69, 20, 67, 96)
```

### ¿Qué es una función?

Las funciones se refieren a procesos que transforman datos de entrada (input) en una salida (output).

En el caso anterior, **c()** es la función que permitió **“concatenar”** (o enlazar) los números 1, 53, 69, 20 y 67 dentro del objeto **a**. De la misma forma, la función **cor.test()** hizo varias tareas sobre los datos de entrada. Por un lado, calculó la correlación de Pearson entre ambos conjuntos de números, obtuvo los intervalos de confianza al 95% para la esa correlación, y además calculó el valor p asociado al coeficiente de correlación. ¡Todo esto con menos de una línea de código!

Tanto **c()** como **cor.test()** son funciones que vienen integradas al instalar R, de modo que forman parte de lo que se conoce como **R base**. No obstante, para realizar tareas más especializadas se necesitan **paquetes** (también llamados **librerías**) que agregan nuevas funciones a R. Estos paquetes descargables se almacenan en el **CRAN (Comprehensive R Archive Network)** dentro de https://www.r-project.org/. Una ventaja de utilizar paquetes del CRAN es que han sido **revisados por pares**, por lo que pueden ser citados en publicaciones científicas. Además, estos paquetes están sujetos a mantención y cuentan con un manual de referencia.

Lo que hacemos en ciencias sociales o de la salud en una sesión de R usual es cargar una “base de datos” (conjunto de datos organizados en filas y columnas), y aplicar funciones sobre columnas (variables) específicas para obtener resultados de interés, como tablas, gráficos, parámetros de modelos estadísticos, predicciones, entre otros.

El proceso descrito se resume en la siguiente figura:

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\funcion.png){width="50%"}

</center>

En jerga de R, el hecho de aplicar una función se denomina “llamar” a esa función.

Si bien las funciones se pueden aplicar utilizando su configuración por defecto, generalmente es de interés controlar algunos parámetros de la función. Estos parámetros se conocen como **argumentos**, y se pueden pensar intuitivamente como “opciones” que permiten especificar con mayor precisión del resultado que se desea obtener. Por ejemplo, la función **cor.test()** entrega por defecto el coeficiente de correlación de Pearson, sin embargo, ¿qué ocurre si se necesita el coeficiente de correlación de Spearman? Para lograr esto se define el argumento **method**, solicitando explícitamente la correlación de Spearman.

```{r}
a <- c(1, 53, 69, 20, 67)
b <- c(2, 43, 89, 30, 50)

cor.test(x = a, y = b, method = "spearman")
```

Esto permite ilustrar cómo el ajuste de un argumento controla y modifica la salida de la función.

## Interfaz de Rstudio

La ventana de Rstudio se ve de la siguiente forma.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\pantallarstudio.png){width="110%"}

</center>

Hay cuatro secciones distintas con funcionalidades diferentes.

### Script

El script de R es básicamente una hoja donde puedes escribir todos los códigos que te interesa ejecutar y registrar. Por ejemplo, aquí primero escribí el código para crear un objeto llamado **algunos_numeros** que contiene un conjunto de números diferentes. Luego escribí el nombre del objeto generado (**algunos_numeros**) para que R muestre la información que contiene.

```{r}
algunos_numeros <- c(24, 13, 28, 14)
algunos_numeros 
```

Para ejecutar estos códigos solo se necesita seleccionarlos y presionar **Run**. Un atajo que suelo utilizar para correr el código es **ctrl + enter**.

Al correr el código notarás que los resultados no aparecen dentro del script, sino en una ventana diferente.

El símbolo **#** es una herramienta útil en el script. Todo lo que se encuentre a la derecha del **#** será leído como un comentario y no como código de R.

Puedes guardar un script en la carpeta que desees haciendo click en el símbolo de disquete.

### Consola

La ventana donde se muestran los resultados de ejecutar un código se denomina consola. Como puedes notar, al ejecutar el código de un script vuelve a aparecer en la consola. Esto evita confusiones respecto a la información de salida. Tal como se esperaba, correr el código del nombre del objeto arroja la información sobre los números que contiene.

### Entorno

Otro efecto colateral de haber corrido el código **algunos_numeros <- c(24, 13, 28, 14)**, es que ahora el objeto **algunos_numeros** pasará a ser almacenado en el **entorno**.

Esto permitirá que R recuerde el objeto y su contenido. Sin embargo, puedes eliminar los objetos del entorno presionando el símbolo de escoba. Al hacer esto, notarás que ejecutar el código algunos_numeros arrojará un error en la consola, ya que se ha “olvidado” dicho objeto. 

La información que no sea asignada a un objeto no será recordada de manera posterior durante la sesión de R. He ahí la diferencia entre los siguientes códigos:

```{r}
mean(algunos_numeros)

promedio_numeros <- mean(algunos_numeros)
```

La función **mean()** permite obtener el promedio de un conjunto de valores numéricos. En este caso, **mean(algunos_numeros)** entrega el promedio de los dígitos incluidos en **algunos_numeros**. El resultado aparece impreso en la consola de la manera usual.

Sin embargo, **promedio_numeros <- mean(algunos_numeros)** no entrega el promedio de los números. La razón es que este código solo asigna el promedio de **algunos_numeros** al objeto **promedio_numeros**, no pide a R que imprima el resultado del contenido del objeto. Para obtener esta información, se necesita escribir el nombre del objeto nuevamente.

```{r}
promedio_numeros
```

### Visor, gráficos y ayuda

En la sección de visor, gráficos y ayuda se pueden visualizar gráficos y también obtener información detallada sobre las funciones. 

Por ejemplo, la función **hist()** permite crear un histograma sobre los dígitos de **algunos_numeros**, el cual aparecerá en la pestaña **plots**.

Para obtener información adicional sobre el funcionamiento de **hist()**, se puede usar **?hist**. 

# Importación, edición y exportación de datos en R

## Directorio de trabajo

Para cargar archivos en R es muy importante conocer el **directorio de trabajo** que está utilizando Rstudio. El directorio de trabajo se refiere a la carpeta donde se encuentran los archivos que se manejarán en R. Cualquier archivo que se quiera cargar en R debe estar en el directorio de trabajo, y cualquier archivo exportado desde R se almacenará en el directorio de trabajo.

Para conocer el directorio de trabajo actual se usa **getwd()**:

```{r}
getwd()
```

Para **cambiar el directorio de trabajo** a otra carpeta se usa la función **setwd()**. Se debe procurar que los **/** de la dirección estén en la orientación correcta.

```{r}
setwd("C:/Users/jorge/Desktop/DOCENCIA/A. Taller Introducción a R para ciencias sociales y de la salud/SINTESIS BOOKDOWN/BOOKDOWN2")
```

**Nota:** Si guardan un script de R en una carpeta específica, cuando vuelvan a abrirlo directamente haciendo doble click sobre él, automáticamente se fijará esa carpeta como directorio de trabajo.

El directorio de trabajo por defecto se puede cambiar en **Global options** dentro de **Tools**.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\manual_wd.png){width="70%"}

</center>

## Importación de datos

### Importación de datos CSV con readr 

**readr** es una librería que permite importar datos separados por comas (**csv**) desde Excel. 

Para usar la librería **readr** se debe instalar primero usando la función **install.packages()**.

```{r}
# install.packages("readr")
```

Una vez instalada una librería, es necesario activarla usando **library()**.

```{r}
library(readr)
```

Se utilizará la función **read_csv()** de **readr** para importar la base de datos **datoscancercsv**. Esta se asigna al objeto llamado **datos**.

```{r}
setwd("C:/Users/jorge/Desktop/DOCENCIA/A. Taller Introducción a R para ciencias sociales y de la salud/SINTESIS BOOKDOWN/BOOKDOWN2")

datosCSV <- read_csv("datoscancercsv.csv")
```

Nota que: 

A. El nuevo objeto **datos** pasa a ser almacenado en el entorno.
B. Hacer click sobre el nombre del objeto permite acceder al **visor de datos**.

### Desactivar o remover librería

Una librería se puede desactivar del entorno actual utilizando la función **detach()**, o bien se puede desinstalar de R usando **remove.packages()**.

```{r}

# Desactiva readr

# detach("package:readr", unload = TRUE)

# Desinstala readr

# remove.packages("readr")

```

###	Importación de datos de Excel con readxl 

Para importar datos desde una hoja de Excel se puede usar la función **read_excel()** de la librería **readxl**.

```{r}
# install.packages("readxl")

library(readxl)

datosEXCEL <- read_excel("cyclingexcel.xlsx")
datosEXCEL
```

### Importación desde SPSS o Stata con haven

Para importar datos desde SPSS o Stata se pueden usar las funciones **read_sav()** o **read_dta()** de la librería **haven**, respectivamente.

```{r}

# install.packages("haven")

library(haven)
datosSPSS <- read_sav("datosspss.sav")
```

o

```{r}
datosSTATA <- read_dta("datosstata.dta")
datosSTATA
```

Una ventaja de trabajar con datos importados desde SPSS es que los **valores perdidos definidos por el usuario (ej. 999) se convertirán automáticamente al formato que utiliza R (.).**

## Edición de datos

La eliminación o modificación de datos específicos de una base de datos se puede hacer en otros programas antes de pasarla a R.

Para editar datos específicos dentro de R, se puede usar la librería **DataEditR**.

```{r}
# install.packages("DataEditR")

library(DataEditR)
```

La función **data_edit()** abrirá un editor de datos con la siguiente forma:

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\edit1.png){width="100%"}

</center>

Para editar una base de datos existente, se debe aplicar la función **data_edit()** sobre el objeto que almacena esa base de datos. De la misma forma, se necesita asignar el resultado de la edición a un nuevo objeto para guardar los cambios realizados.

```{r}
# datosSPSSeditado <- data_edit(datosSPSS)
```

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\edit2.png){width="100%"}

</center>

Para ilustrar el funcionamiento del editor, se cambiarán los datos de sexo de los sujetos 1, 4 y 7 por un **999**.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\edit3.png){width="100%"}

</center>

Para completar el cambio se debe presionar el símbolo de **sincronizado** y luego **done**.

Al revisar el visor de datos se puede chequear el cambio.

**Nota:** Este editor puede volverse lento cuando la base de datos es demasiado grande.

## Exportación de datos

Los siguientes códigos ilustran cómo exportar los datos desde R a otro formato:

-	Para exportar datos a formato **csv** se usa la función **write_csv()** de **readr**:

```{r}
write_csv(datosSTATA, file = "datosstata2.csv")
```

-	Para exportar datos a formato **xlsx** se usa la función **write_xlsx()** de **writexl**:

```{r}
# install.packages("writexl")
library(writexl)
write_xlsx(datosSTATA, path = "datosStata3")
```

- Para exportar datos a formato **sav (SPSS)** se usa la función **write_sav()** de **haven**:

```{r}
write_sav(datosSTATA,path = "datosStata4")
```

Los nuevos archivos se almacenarán por defecto en el directorio de trabajo.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\expo.png){width="100%"}

</center>

# Manejo de datos

## Introducción al tidyverse

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\logotidy.png){width="40%"}

</center>

El término tidyverse hace referencia a una colección de paquetes de R que comparten una **filosofía de diseño**, una **gramática** y una **estructura** subyacentes.

El tidyverse entrega herramientas para llevar a cabo la mayor parte de tareas rutinarias de análisis de datos, desde la importación de una base de datos a R hasta la comunicación de resultados mediante reportes, pasando por la manipulación y visualización de los datos. 

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\flujo.png){width="60%"}

</center>

La filosofía del tidyverse se fundamenta en cuatro principios:

**a.	Foco centrado en el humano:** El tidyverse busca facilitar el manejo de R en usuarios nuevos sin experiencia en programación. La memoria de trabajo es limitada y reducir la carga cognitiva ayudará aprendiz.

**b.	Consistencia:** Lo que se aprende sobre una función o paquete se puede aplicar en otro.

**c.	Compuesto:** Ayudar a resolver problemas complejos reduciéndolos a pequeñas piezas.

**d.	Inclusión:** El tidyverse es también la comunidad de personas que lo implementan.

### ¿Qué paquetes incluye el tidyverse?

Entre otros, se incluyen:

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\packages.png){width="40%"}

</center>

## El paquete dplyr

El paquete **dplyr** contiene funciones para manejar y transformar datos. **dplyr** se basa en una **gramática de la manipulación de datos**, donde cada función se puede pensar como un **verbo** que actúa sobre un objeto (dataset).

```{r}
library(dplyr)
```

Al activar la librería **dplyr**, se sobrescriben algunas funciones de R base u otras librerías. Esto se denomina **enmascaramiento**. Por ejemplo, dplyr contiene una función **select()** que no opera de la misma forma que la función **select()** de R base. Para especificar el uso de una función basada en un paquete específico se utiliza la expresión **nombre_del_paquete::**. Por ejemplo, **dplyr:: select()** o **stats:: select()**. Las funciones de R base usan el paquete **stats**.

La mayoría de las tareas de manejo de datos se pueden realizar con cinco verbos de **dplyr**:

- **filter()** selecciona observaciones (casos) según sus valores de una o más variables.
-	**arrange()** reordena las filas.
-	**select()** selecciona variables por su nombre.
-	**mutate()** crea nuevas variables a partir de variables existentes.
-	**summarize()** colapsa valores en un único resumen.

Los verbos de dplyr tienen en común que:

-	El primer argumento es un dataframe (la “base datos” que se carga en Rstudio).
-	El siguiente argumento describe lo que se hará con los datos usando los nombres de las variables sin comillas.
-	El resultado es un nuevo dataframe.

Los verbos de dplyr toman como input un dataset sobre el cual se aplican las operaciones especificadas, de manera que se obtiene un nuevo dataset. **Las funciones de dplyr nunca modifican el dataset de input**. Por lo tanto, para guardar el resultado de utilizar un verbo de dplyr, se necesita asignar este resultado a un nuevo objeto con el operador de asignación (**<-**).

### Datos de ejemplo

Para ilustrar la implementación de los verbos de dplyr se utilizará el dataset **datosspss.sav**. El libro de códigos se encuentra en el excel **codigos.xlsx**.

```{r}
library(readxl)
codigos <- read_xlsx("codigos.xlsx")
print(codigos, n = 30)
```

Se activa **haven** y se importan los datos.

```{r}
library(haven)

datosSPSS <- read_sav("datosspss.sav")
```

### filter()

Permite crear subconjuntos de filas (casos) según los valores de columnas (variables). 

El primer argumento es el nombre del dataframe. El segundo y tercer argumento son expresiones que filtran el dataset.

El filtrado se realiza usando operadores lógicos: 

-	">"
-	">="
-	"<"
-	"<=" 
-	"== (igual)"
-	"!= (no es igual)".

Se seleccionan únicamente individuos de bajo nivel socioeconómico.

```{r}
filter(datosSPSS, NSE == "Bajo")
```

Se pueden combinar condiciones de filtrado utilizando **operadores Booleanos**: 

-	& significa y.
-	| significa o.

Se seleccionan individuos hombres y de bajo nivel socioeconómico.

```{r}
filter(datosSPSS, sexo == 1 & NSE == "Bajo")
```

Se seleccionan individuos que no sean de nivel socioeconómico medio o con edad mayor a 60 años.

```{r}
filter(datosSPSS, NSE != "Medio" | edad > 60)
```

También se puede filtrar por una **serie de valores específicos** usando el operador **%in%**. El formato es variable **%in% c(valores específicos)**.

Se seleccionan casos con edad de 18, 21 y 25 años.

```{r}
filter(datosSPSS, edad %in% c(18, 21, 25))
```

Se puede filtrar por valores mínimos, máximos y otros criterios numéricos.

Se filtran casos que tienen el puntaje mínimo en el primer ítem de depresión (1).

```{r}
filter(datosSPSS, depre1 == min(depre1))
```

La variable **depre4** tiene datos perdidos (codificados en R como **NA**). Para seleccionar los casos con datos perdidos se utiliza la función **is.na()**.

```{r}
filter(datosSPSS, is.na(depre4))
```

Por el contrario, para seleccionar todos los casos que no son **NA** de **depre4** se utiliza **!is.na()**.

```{r}
filter(datosSPSS, !is.na(depre4))
```

Para remover todos los casos con datos perdidos de un dataset se utiliza **complete.cases()**.

```{r}
filter(datosSPSS, complete.cases(datosSPSS))
```

### slice()

La función **slice()** permite seleccionar filas especificando su posición.

Se puede especificar una fila con su número de fila, o un rango de filas desde un número específico a otro número específico usando el formato **A:B**.

Se selecciona el individuo de la fila 9.

```{r}
slice(datosSPSS, 9)
```
 
Se seleccionan los individuos desde la fila 3 a la fila 8.

```{r}
slice(datosSPSS, 3:8)
```
 
Se puede utilizar **slice_min()** o **slice_max()** para obtener las observaciones superiores o inferiores según una variable y porcentaje que se necesita ver.

Se selecciona el 10% de las personas más jóvenes y el 20% de las personas de mayor edad.

```{r}
slice_min(datosSPSS, edad, prop = 0.10)
 
slice_max(datosSPSS, edad, prop = 0.20)
```

También se puede usar **slice_sample()** para obtener una muestra aleatoria de un conjunto de datos.

Se seleccionan 15 participantes al azar con reposición.

```{r}
slice_sample(datosSPSS, n = 15, replace = FALSE)
```

### select()

La función **select()** permite crear subconjuntos de columnas (variables) específicas de un dataset. Las columnas se ordenan según su ingreso a **select()**.

Se seleccionan únicamente las variables nivel socioeconómico, felicidad y satisfacción con la vida.

```{r}
select(datosSPSS, NSE, felicidad, satis_vida)
```
 
Se pueden seleccionar secuencias de columnas que están seguidas en el dataset.

Se seleccionan todas las columnas desde el primer al cuarto ítem de depresión y la felicidad.

```{r}
select(datosSPSS, depre1:depre4, felicidad)
```
 
Otra opción es seleccionar todas menos alguna(s) columna. Esto se logra agregando el signo menos **(-)** antes de nombrar la columna(s).

Se seleccionan todas las variables menos la **edad**.

```{r}
select(datosSPSS, -edad)
```

Se seleccionan todas las variables menos los primeros ítems de ansiedad y depresión.

```{r}
select(datosSPSS, -c(ansiedad1, depre1))
```
 
Se seleccionan todas menos las variables que están entre **sexo** y **región**.

```{r}
select(datosSPSS, -c(sexo:region))
```
 
**select()** se puede complementar con funciones de ayuda:

-	**starts_with(“abc”)**

Empareja nombres que comienzan con **“abc”**.

-	**ends_with(“xyz”)**

Empareja nombres que terminan con **“xyz”**.

-	**contains(“ijk”)**

Empareja nombres que contienen **“ijk”**.

-	**num_range(“x”, 1:3)**

Empareja **x1**, **x2** y **x3**.

Se seleccionan todas las variables que comienzan con **“sustan”**.

```{r}
select(datosSPSS, starts_with("sustan"))
```
 
Se seleccionan las variables que terminan con **“2”**.

```{r}
select(datosSPSS, ends_with("2"))
```
 
Se seleccionan variables que contienen **“da”**.

```{r}
select(datosSPSS, contains("da"))
```
 
Se seleccionan la variable **sexo** y las variables desde **depre1** a **depre3**.

```{r}
select(datosSPSS, sexo, num_range("depre", 1:3))
```
 
Se borran todas las variables que contengan **“ansiedad”**.

```{r}
select(datosSPSS, -contains("ansiedad"))
```
 
Seleccionar las variables **sexo** y desde el segundo hasta el cuarto ítem de depresión.

```{r}
select(datosSPSS, sexo, num_range("depre", 2:4))
```
 
Se remueven todas las variables que terminan con **o**.

```{r}
select(datosSPSS, -ends_with("o"))
```

### arrange()

La función **arrange()** permite ordenar las filas (casos) de una o más columnas (variables). Por defecto, las filas se ordenan de manera **creciente**.

Se ordenan los datos por edad de menor a mayor edad.

```{r}
arrange(datosSPSS, edad)
```

Las filas de una columna se ordenan de manera decreciente con **desc()**.

```{r}
arrange(datosSPSS, desc(edad))
```

Los valores perdidos (**NA**) siempre se ubican al final, independientemente de si el orden es creciente o decreciente.

### relocate()

**relocate()** permite cambiar la posición de las columnas con el formato **relocate(datos, variable, nueva ubicación)**.

La nueva ubicación se especifica con los argumentos **.before =** o **.after =**, indicando antes o después de qué columnas se quiere ubicar la variable.

Se mueve la variable **ansiedad2** después de **ID**.

```{r}
relocate(datosSPSS, ansiedad2, .after = ID)
```

Si no se especifica una ubicación, la variable se mueve por defecto al inicio del dataset.

```{r}
relocate(datosSPSS, edad)
```

### rename()

**rename()** permite cambiar el nombre de una o más columnas.

Se cambia el nombre de NSE a Nsocioeconomico.

```{r}
rename(datosSPSS, Nsocioeconomico = NSE)
```

### mutate()

Sirve para crear nuevas columnas (variables) de acuerdo a columnas existentes.

Se crea la variable **depresion_total** como el promedio de los cuatro ítems de depresión.

```{r}
mutate(datosSPSS, depresion_total = (depre1 + depre2 + depre3 + depre4)/4)
```

También se pueden remover variables usando **mutate()**.

Se remueve la variable **sexo**.

```{r}
mutate(datosSPSS, sexo = NULL)
```

Se puede usar **mutate()** para crear una variable con el promedio de una columna.

Se crea la variable **Pestres** con el promedio de estrés de la muestra.

```{r}
mutate(datosSPSS, Pdepre4 = mean(depre4))
```

Sin embargo, la columna solo contiene **NA**. Esto se puede visualizar de mejor forma asignando el resultado de mutate a un nuevo objeto y examinándolo con el visor de datos.

```{r}
datos_ejemplo <- mutate(datosSPSS, Pdepre4 = mean(depre4))

# Revisar visor de datos
```

Por defecto, **mutate()** agrega las nuevas columnas al final del dataset. Esto se puede modificar usando los argumentos **.after =** y **.before =** .

Se crea **Pdepre4** y se ubica inmediatamente después de **edad**.

```{r}
mutate(datosSPSS, Pdepre = mean(depre4, na.rm = TRUE), .after = edad)      
```

Se pueden aplicar operaciones a múltiples columnas usando **across()**.

Se transforman simultáneamente los puntajes de felicidad y satisfacción con la vida a puntajes z utilizando la función **scale()**.

```{r}
mutate(datosSPSS, across(c(felicidad, satis_vida), scale))
```

#### Recodificación con mutate()

Con **mutate()** se puede reemplazar uno o más valores de una variable por otro valor específico utilizando **replace()**.

Se reemplazan los valores iguales a 2 en **ansiedad1** y **ansiedad2** por **999**.

```{r}
datosSPSS %>% mutate(ansiedad1 = replace(ansiedad1, ansiedad1 == 2, 999),
                     ansiedad2 = replace(ansiedad2, ansiedad2 == 2, 999))
```

Para recodificar una variable valor por valor se puede usar **case_when()** en complemento con **mutate()**. Se ilustra esto creando antes una nueva variable (actfisica), que indica la cantidad de días en la semana que las personas realizan actividad física (0 a 7).

```{r}
datosSPSS$actfisica <- sample(0:7, 1000, replace = TRUE)
```

**Nota:** la función **sample()** crea una secuencia de números en el rango especificado dentro del primer argumento (0 a 7), del tamaño especificado en el segundo argumento (1000 números). El argumento **replace = TRUE** permite que los números se puedan repetir para alcanzar el valor de 1000.

Se usa **case_when()** para recodificar actfisica de manera que el puntaje más bajo sea el 1 en lugar de 0.

```{r}
datosSPSS %>% mutate(actfisica = case_when(actfisica == 0 ~ 1,
                                           actfisica == 1 ~ 2,
                                           actfisica == 2 ~ 3,
                                           actfisica == 3 ~ 4,
                                           actfisica == 5 ~ 6,
                                           actfisica == 6 ~ 7,
                                           actfisica == 7 ~ 8))
```

Al asignar el resultado a un nuevo objeto **A**, se observa que ahora el rango de valores de actfisica va de 1 a 8 (en lugar de 0 a 7).

La función **case_when()** también es útil para recodificar variables cualitativas.

Se cambian los valores de sexo a femenino y masculino.

```{r}
datosSPSS %>% mutate(sexo = case_when(sexo == 1 ~ "Masculino",
                                      sexo == 2 ~ "Femenino"))
```

Para discretizar una variable cuantitativa en categorías, es útil combinar **mutate()** con la función **ifelse()**.

Se crea la variable **categorías_edad** que divide la edad en tres categorías.

-	La categoría 1 incluye casos con edad igual o menor a 30 años.
-	La categoría 2 incluye casos con edades mayores a 30 e iguales o menores a 40 años.
-	La categoría 3 incluye casos con edades mayores a 40 años.

```{r}
datosSPSS %>% mutate(categorias_edad = ifelse(edad <= 30, 1,
                                       ifelse(edad > 30 & edad <= 40, 2,
                                                                    3)))
```

### transmute()

**transmute()** es igual que **mutate()** a excepción de que solo retiene las columnas generadas, eliminando las originales.

Se crea un puntaje total de depresión como la sumatoria de los cuatro ítems desde **depre1** a **depre4**, eliminando los ítems originales.

```{r}
transmute(datosSPSS, depre_tot = depre1 + depre2 + depre3 + depre4)
```

### distinct()

La función **distinct()** permite ver las filas únicas en un dataset (valores únicos de una variable).

Se muestran los valores observados del primer ítem de ansiedad.

```{r}
distinct(datosSPSS, ansiedad1)
```

## Combinación de operaciones con el operador pipe (%>%)

El operador **%>%** permite combinar distintas operaciones simultáneamente. 

**%>%** toma el objeto a la izquierda y lo pasa como el primer argumento de la función especificada a la derecha.

Se crea un dataset donde primero se filtran solo hombres que consumen alcohol. Luego se seleccionan las variables de depresión y ansiedad y estrés. Finalmente, se crea un puntaje total para depresión y ansiedad, respectivamente.


```{r}
datosSPSS %>% filter(sexo == 1 & sustan1 == 1) %>% 
              select(depre1, depre2, depre3, depre4, ansiedad1, ansiedad2) %>% 
              mutate(total_depresion = (depre1 + depre2 + depre3 + depre4),
                     total_ansiedad = (ansiedad1 + ansiedad2))
```

### group_by()

Los verbos de dplyr se pueden usar en conjunto con **group_by()**, haciendo que cada función opere sobre cada grupo individual por separado en lugar del dataset completo.

Por sí sola, la función **group_by()** no es muy útil, sin embargo, lo es al complementarla con otros verbos.

#### Resúmenes agrupados: group_by() con summarize()

La función **group_by()** permite obtener estadísticos agrupados al complementarla con **summarize()**.

**summarize()** por sí sola permite calcular el promedio de edad de la muestra completa.

```{r}
summarize(datosSPSS, Medad = mean(edad))
```

Al usar **group_by()** primero, se divide el dataset según los grupos de una variable. Así, las funciones (ej. **mean()**) se aplican sobre cada grupo separado, entregando estadísticos agrupados.

Se calculan los promedios de edad según los grupos de nivel socioeconómico.

```{r}
datosSPSS %>% group_by(NSE) %>% 
              summarize(Medad = mean(edad))
```

Al calcular los promedios y desviaciones estándar grupales de **depre4**, se obtiene **NA** debido a que hay datos perdidos en algunos grupos.

```{r}
datosSPSS %>% group_by(NSE) %>% 
              summarize(Mdepre4 = mean(depre4),
                        DEdepre4 = sd(depre4))
```

Para resolver el problema se remueven los datos perdidos del cálculo de la función con el argumento **na.rm = TRUE**.

```{r}
datosSPSS %>% group_by(NSE) %>% 
              summarize(Mdepre4 = mean(depre4, na.rm = TRUE),
                        DEdepre4 = sd(depre4, na.rm = TRUE))
```

Se puede obtener el conteo de los casos con o sin **NA** utilizando **sum(is.na(x))**.

Número de casos con datos perdidos y no perdidos en **depre4** según nivel socioeconómico.

```{r}
datosSPSS %>% group_by(NSE) %>% 
              summarize(Nperdido = sum(is.na(depre4)),
                        Nnoperdido = sum(!is.na(depre4)))
```

Se puede obtener un conteo simple del número de filas (casos) por grupo con **n()**.

```{r}
datosSPSS %>% group_by(NSE) %>% 
              summarize(conteo = n())
```

También se puede agrupar por múltiples variables, donde cada resumen aplica para un nivel de la agrupación.
Se calculan los promedios y desviaciones estándar grupales según sexo y nivel socioeconómico.

```{r}
datosSPSS %>% group_by(sexo, NSE) %>% 
              summarize(Mdepre4 = mean(depre4, na.rm = TRUE),
                        DEdepre4 = sd(depre4, na.rm = TRUE))
```

Se calcula el conteo de filas (casos) por sexo y nivel socioeconómico.

```{r}
datosSPSS %>% group_by(sexo, NSE) %>% 
              summarize(conteo = n())
```

Se puede remover el agrupamiento con la función **ungroup()**.

```{r}
datosSPSS %>% group_by(sexo, NSE) %>%
              ungroup() %>% 
              summarize(conteo = n())
```

#### Mutaciones agrupadas: group_by() con mutate()

La combinación de **group_by()** con **mutate()** permite hacer que los resúmenes formen parte del dataset original.

Se quiere agregar el promedio grupal de **ansiedad1** según el nivel socioeconómico como una nueva columna (**MGansiedad1**).

```{r}
datosSPSS %>% group_by(NSE) %>% 
              mutate(MGansiedad1 = mean(ansiedad1, na.rm = TRUE)) %>% 
              ungroup()

```

#### Filtros agrupados: group_by() con filter()

La combinación de **group_by()** con **filter()** permite filtrar casos según características grupales.
Se seleccionan individuos de regiones que tienen un promedio menor que 1 en el primer ítem de depresión o mayor a 2.6 en el primer ítem de ansiedad.

```{r}
datosSPSS %>% group_by(region) %>% 
              filter(mean(depre1) < 1 | mean(ansiedad1) > 2.7)
```

Se corrobora que los grupos de regiones cumplen con las condiciones de filtrado (promedio de **depre1 < 1** o **ansiedad1 > 2.7**).

```{r}
datosSPSS %>% group_by(region) %>% 
              summarize(Mdepre1 = mean(depre1),
                        Mansiedad1 = mean(ansiedad1))
```

Se seleccionan casos con puntajes mayores al promedio de **ansiedad1** de su respectivo grupo de región.

```{r}
datosSPSS %>% group_by(region) %>% 
              filter(ansiedad1 > mean(ansiedad1))
```

Se filtran casos de según combinaciones de sexo y nivel socioeconómico que cuentan con menos 30 casos.

```{r}
datosSPSS %>% group_by(NSE, sexo) %>%  
              filter(n() < 30)
```

Se corrobora que estas combinaciones de sexo y nivel socioeconómico son aquellas que muestran un número de casos inferior a 30.

```{r}
datosSPSS %>% group_by(NSE, sexo) %>%  
              summarize(N = n())
```

Se filtran casos de según combinaciones de sexo y nivel socioeconómico que cuentan con menos 30 casos, y que además son mujeres.

```{r}
datosSPSS %>% group_by(NSE, sexo) %>%  
              filter(n() < 30, sexo == 2)
```

# Estadística descriptiva

## Datos de ejemplo: Titanic

Se carga el **tidyverse**, y los datos **titanic_train** del paquete **titanic**.

```{r}

# se requiere tener instalado el paquete titanic
# install.packages("titanic")

library(tidyverse)
data(titanic_train, package = "titanic")

# Unidad de análisis: Pasajeros del Titanic

# Variables: 
# PassengerId – Número único de cada pasajero.
# Survived – Un entero que denota supervivencia (1 = Sobrevivió, 0 = Murió).
# Pclass – Si un pasajero estaba en primera, segunda o tercera clase.
# Name – Vector de caracteres de los nombres de pasajeros.
# Sex – Vector de caracteres con “male” y “female”.
# Age – Edad del pasajero.
# SibSp – El número combinado de hermanos y esposas a bordo.
# Parch – Número combinado de padres y niños a bordo.
# Ticket – Vector de caracteres con el número de ticket de cada pasajero.
# Fare – La cantidad de dinero que cada pasajero pagó por su ticket.
# Cabin – Vector de caracteres del número de cabina de cada pasajero.
# Embarked – Un vector de caracteres que indica el origen del pasajero.
```

Se asignan los datos **titanic_train** como **tibble** al objeto **titanicTib**.

```{r}
titanicTib <- as_tibble(titanic_train)
titanicTib
```

## Estadísticos descriptivos para variables cuantitativas

Se puede usar la función **summary()** sobre una variable cuantitativa para un resumen rápido.

```{r}
summary(titanicTib$Fare)
```

La función **describe()** de la librería **psych** entrega más estadísticos descriptivos, donde el argumento **na.rm** controla si se remueven los datos perdidos (por defecto es **TRUE**). Además, el argumento **IQR = TRUE** permite obtener el rango intercuartílico.

```{r}
library(psych)
describe(titanicTib$Fare, IQR = TRUE)
```

Se obtiene:

-	Número de casos (**n**) con datos en la variable.
-	Promedio (**mean**).
-	Desviación estándar (**sd**).
-	Media recortada (**trimmed**).
-	Desviación absoluta de la mediana (**mad**).
-	Mínimo (**min**).
-	Máximo (**max**).
-	Rango (**range**).
-	Asimetría (**skew**).
-	Curtosis (**kurtosis**).
-	Error estándar (**se**).
-	Rango intercuartílico (**IQR**).

Para cambiar el **número de dígitos reportados** se puede guardar el resultado de **describe()** en un objeto y cambiar el número con el argumento **digits**.

```{r}
desc <- describe(titanicTib$Fare)
print(desc, digits = 4)
```

## Estadísticos descriptivos agrupados para variables cuantitativas

La función **describeBy()** describe una variable cuantitativa dentro de cada categoría de una variable de agrupación.

```{r}
describeBy(titanicTib$Fare, titanicTib$Pclass, IQR = TRUE)
```

## Estadísticos descriptivos para una variable cualitativa

La función **freq()** de la librería **summarytools** crea una tabla con las frecuencias absolutas y relativas de una variable cualitativa.

```{r}
library(summarytools)
freq(titanicTib$Pclass)
```

La tabla se puede ordenar según las frecuencias con el argumento **order = “freq”**.

```{r}
freq(titanicTib$Pclass, order = "freq")
```

Los siguientes argumentos modifican la información que entrega la tabla:

- **report.nas** controla si se agrega una fila sobre las frecuencias de los datos perdidos.
- **totals** controla si se agrega la fila con el total de frecuencias absolutas.
-	**cumul** controla si se agrega una columna con los porcentajes acumulados.
-	**headings** controla si se agrega información general sobre la tabla.

```{r}
freq(titanicTib$Pclass, order = "freq",
                        report.nas = FALSE,
                        totals = FALSE,
                        cumul = FALSE,
                        headings = FALSE)
```

## Tabla de contingencia para dos variables cualitativas

La función **ctable()** de **summarytools** entrega una tabla de contingencia. La variable de las filas se define con el argumento **x**, y la variable de las columnas se define con el argumento **y**. Los porcentajes por fila o columna se controlan con el argumento **prop** (**“r”** por **fila**, **“c”** por **columna**, y **“t”** por **totales**). 

La función **ctable()** requiere las variables estén definidas como cualitativas (factores o caracteres).

```{r}

titanicTib$Sex <- as.factor(titanicTib$Sex)
titanicTib$Pclass <- as.factor(titanicTib$Pclass)

ctable(x = titanicTib$Sex, 
       y = titanicTib$Pclass,
       prop = "r",
       headings = FALSE)
```

Se puede agregar una **prueba de chi-cuadrado** con el argumento **chisq**.

```{r}
ctable(x = titanicTib$Sex, 
       y = titanicTib$Pclass,
       prop = "r",
       headings = FALSE,
       chisq = TRUE)
```

# Estructuras de datos y funciones básicas de R

## Tipos de datos

R permite manejar diferentes tipos de datos:

-	**Double/Numeric:** Doble/Numérico.
-	**Integer:** Entero.
-	**Character:** Carácter.
-	**Logical:** Lógico.
-	**Complex:** Complejo.
-	**Raw:** Bruto.

En R, los datos se almacenan en diferentes estructuras, que típicamente son vectores atómicos, listas, matrices o dataframes.

## Vectores atómicos

Los vectores atómicos son vectores que almacenan datos de manera unidimensional.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\vector.png){width="30%"}

</center>

Cada vector atómico puede guardar **solo un tipo de dato**.

Se pueden crear con la función **c()** que permite **“concatenar”** diferentes datos.

```{r}
conjunto <- c(1, 2, 3, 4, 5, 6)
conjunto
```

La función **c()** también permite combinar vectores en un nuevo vector.

```{r}
masnumeros <- c(100, 140, 88, 40)
masnumeros
c(conjunto, masnumeros)
```

El nuevo vector combina, en orden, los vectores **conjunto** y **masnumeros**.

La función **is.vector()** permite probar si un objeto es un vector. Esta arroja **TRUE** si el objeto corresponde a un vector, y **FALSE** si no lo es.

```{r}
is.vector(conjunto)
```

Para determinar el número de valores en el vector se usa la función **length()**.

```{r}
conjunto
length(conjunto)
```

El número de elementos en el conjunto es **6**, lo que corresponde al **tamaño del vector**.

Los vectores atómicos pueden ser valores singulares (vector de tamaño 1). Estos se suelen llamar **escalares**.

```{r}
conjunto <- 10
conjunto
```

Los vectores atómicos se clasifican según el **tipo de dato** que almacenan.

### Vectores dobles/numéricos

Los vectores dobles (**double**), también referidos como vectores numéricos (**numeric**), almacenan números positivos o negativos, con o sin decimales.

La función **typeof()** sobre un vector atómico informa el tipo de dato que lo compone.

```{r}
typeof(conjunto)
```

Los vectores numéricos se pueden usar en operaciones matemáticas también llamadas **operaciones vectorizadas**.

```{r}
x <- c(1, 2, 3)
x
x + 10
y <- c(10, 20, 30)
y
y * 10
y - x
```

Cada operación (suma y multiplicación) se aplicó a cada elemento de los vectores, entregando un vector del mismo tamaño que el original.

Cuando los vectores involucrados son de tamaño diferente, R **recicla** el vector más pequeño hasta obtener el tamaño del vector más grande. Al realizar **x * 10**, **x** funcionó como un vector de tamaño 3, aunque 10 era un vector de tamaño 1.

Implícitamente, R **recicló el 10** para crear un vector de “dieces”. Dicho de otra forma, cuando R calcula **x * 10**, en realidad calcula **x * c(10, 10, 10)**.

Si un vector más corto no se puede dividir en el tamaño del vector más grande, R aplica **reciclado** entregando una advertencia:

```{r}
z <- c(1, 2, 3, 4)
x <- c(0, 10, 100)
z * x
```

#### Secuencias de números

El operador de doble punto **“:”** crea secuencias regulares de números, comenzando desde el número especificado a la izquierda del operador, hasta llegar al número a la derecha del operador. Si los dos números de la secuencia son enteros, la secuencia generada será de enteros.

```{r}
numeros <- 1:10
numeros
```

Si algún número de la secuencia es decimal, la secuencia generada será numérica.

```{r}
numeros <- 1.3:10
numeros
```

Otra manera de obtener una secuencia es con la función **seq()**, que permite establecer la cantidad de incremento o reducción de un número al siguiente:

```{r}
seq(1, 10, by = 0.5)

seq(25, -2, by = -2)
```

El argumento **length.out** permite especificar el tamaño de la secuencia, y entrega valores igualmente espaciados desde un número al siguiente.

```{r}
seq(1, 100, length.out = 10)
```

#### Réplicas

La función **rep()** permite replicar valores específicos. El primer argumento es el **número a replicar**, y el segundo argumento (**times**) es el número de réplicas.

```{r}
rep(3, times = 10)
```

También se puede usar **rep()** sobre vectores.

```{r}
rep(c(1, 2, 3), times = 10)
z <- c(3, 6, 9)
rep(z, times = 3)
```

Al usar **rep()** sobre vectores, la salida repite la secuencia completa. Esto se puede evitar utilizando el argumento **each** en vez de **times**.

```{r}
rep(c(1:2), each = 2)

rep(c(1:2), each = 2, times = 2)
```

#### Redondeo

Los valores decimales de una variable numérica se pueden redondear al entero más cercano con la función **round()**.

```{r}
numeros <- sample(0.2:9.33, 10, replace = FALSE)
numeros

numeros <- round(numeros)
numeros
```

### Vectores enteros

Los vectores enteros (**integer**) almacenan números sin decimales.

Para crear un vector entero se escribe el nombre de cada número seguido por una **L**.

```{r}
int <- c(-1L, 2L, 4L)
int

typeof(int)
```

Los números enteros sin la **L** se guarda como **double/numeric**.

### Vectores de caracteres

Un vector de caracteres almacena piezas de texto llamadas como cadenas (**strings**).

Se crea escribiendo los caracteres entre comillas:

```{r}
texto <- c("buen", "dia")
texto

typeof(texto)
```

Una **cadena** puede contener **letras, números o mezclas de letras con números o símbolos**.

Tanto **“1”** como **“uno”** son **cuerdas de carácter**.

Los vectores de caracteres también se pueden crear con la función **c()**.

```{r}
nombre <- c("Jorge", "Schleef")
nombre

class(nombre)

length(nombre)
```

#### Función paste()

La función **paste()** sirve para combinar los elementos de un vector de caracteres, transformándolos en un vector de tamaño 1.

El argumento **collapse** controla el carácter que separa las cadenas que componen el vector inicial.

```{r}
nombre <- c("Mi", "Nombre", "Es", "Jorge", "Schleef")

paste(nombre, collapse = "")

paste(nombre, collapse = "-")
```

#### Nombres

La función **names()** permite ver los nombres asignados a los elementos de un vector atómico:

```{r}
numeros <- 1:6
numeros

names(numeros)
```

El mensaje **NULL** indica que el objeto **numeros** no tiene nombres asignados.

Se pueden agregar nombres como un **vector de caracteres** para cada elemento del objeto.

```{r}
names(numeros) <- c("uno", "dos", "tres", "cuatro", "cinco", "seis")
numeros
```

Al revisar el vector, R muestra los nombres de los elementos del objeto. Sin embargo, los nombres no cambiarán los valores reales del vector.

```{r}
numeros + 1
```

La función **names()** también permite **cambiar** o **eliminar** los nombres de un vector.

```{r}
names(numeros) <- c("one", "two", "three", "four", "five", "six")

names(numeros) <- NULL
numeros
```

### Vectores lógicos

Los vectores lógicos pueden adoptar dos valores: **TRUE** (o **T**) o **FALSE** (o **F**).

Usualmente se producen usando operadores lógicos:

- mayor que (>).
-	menor que (<). 
-	mayor o igual que (>=).
-	menor o igual que (<=).
-	igual (==).
-	no es igual (!=).

```{r}
z <- 1:10

# Evalúa si un elemento de z es mayor que 7

z > 7

# Evalúa si un elemento de z es diferente de 5

z != 5
```

R asume que **TRUE = 1** y **FALSE = 0**, de manera que se pueden usar operaciones matemáticas sobre vectores lógicos.

```{r}
x <- seq(0, 100, by = 5)

# Sumatoria de elementos de x que cumple condiciones específicas

sum(x >= 30)

sum(x == 55)

sum(x != 30)
```

- 15 elementos (números) en el vector x son mayores o iguales que 30.
- 1 elemento (número) en el vector x es igual a 55.
- 20 elementos (números) en el vector x no son iguales a 30.

#### Operadores booleanos

Los operadores booleanos permiten hacer diferentes pruebas lógicas. 

El operador booleano **&** significa **y**, mientras que **|** significa **o**.

Los operadores booleanos se usan entre **dos pruebas lógicas**.

```{r}
a <- c(1, 2 ,3)
b <- c(1, 2 ,3)
c <- c(1, 2, 4)
a == b
b == c
a == b & b == c
```

El resultado es un conjunto de elementos lógicos para la comparación de los elementos de **cada vector en orden**.

#### Funciones all() y any()

Cuando se aplica a un vector lógico:

- La función **all()** arroja **TRUE** si todos los elementos del vector lógico son **TRUE**, y arroja **FALSE** en caso contrario.
- La función **any()** arroja **TRUE** si algún elemento del vector lógico es **TRUE**, y arroja **FALSE** en caso contrario.

```{r}
x <- 10:100
x

all(x == 10)

any(x == 10)

all(x >= 10)

any(x >= 10)
```

#### Coerción implícita

Al combinar dos vectores atómicos de diferente tipo en un único vector, R usa **coerción** para que todos los elementos en el vector resultante sean de la misma clase, debido a que todos los elementos de un vector atómico deben ser del **mismo tipo**.

a. Al combinar un **objeto numérico** y un **objeto de caracter** se crea un **vector de carácter**, donde los números se representan como cadenas.

```{r}
x <- c(1, 2, "a")
x

class(x)
```

b. Al combinar un **objeto numérico** con un **objeto lógico** se crea un **vector numérico** donde **TRUE = 1** y **FALSE = 0**.

```{r}
x <- c(1, 2, TRUE)
x

class(x)
```

c. Al combinar un **objeto numérico** con un **objeto entero** se crea un **vector numérico**.

```{r}
x <- c(1, 2, 10L)
x

class(x)
```

d. Al combinar un **objeto de carácter** con un **objeto lógico** se crea un **vector de carácter**, donde **TRUE** y **FALSE** se representan con **cadenas**.

```{r}
x <- c("a", "b", TRUE, FALSE)
x

class(x)
```

#### Coerción explícita

Se puede hacer que los vectores cambien de tipo explícitamente usando las funciones **as.numeric**, **as.integer**, **as.character** y **as.logical**, que convierten vectores a una clase determinada.

```{r}
x <- 1:10

class(x)

as.numeric(x)
as.character(x)
as.logical(x)
```

Cuando se transforma un vector a vector lógico, R convierte el **1** y todos los números mayores a 1 en **TRUE**.

Cuando R no puede averiguar cómo coaccionar un vector, se producen NA (valores perdidos) con un mensaje de alerta.

```{r}
x <- c("a", "b", "c")
x

class(x)

as.numeric(x)
as.integer(x)
as.logical(x)
```

## Listas

Las listas son un tipo de vector que puede **contener objetos de diferente clase** (ej. vectores atómicos de distinto tipo), y **almacenar vectores de diferente tamaño**.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\Listas.png){width="25%"}

</center>

Las listas se crean con la función **list()**, donde cada elemento de la lista se separa por una coma **“,”**.

**Ejemplo:** lista de escalares.

```{r}
x <- list(10, "a", TRUE)
x
```

Cada elemento de la lista comienza con **doble paréntesis cuadrado [[]]**.

El primer elemento es **numérico (10)**, el segundo elemento es un **carácter (“a”)**, y el tercer elemento es un **valor lógico (TRUE)**.

Las listas pueden tener **nombres para sus elementos**.

```{r}
x <- list(numerito = 10, letra = "a", verdadero = TRUE)
x
```

Ahora cada elemento de la lista comienza con el **nombre** asignado en lugar de doble paréntesis cuadrado.

**Ejemplo:** lista de vectores completos.

```{r}
lista <- list(letras = letters,
              numeros = 10:20,
              logico = (seq(1, 50, 10) > 10))
lista
```

La secuencia contiene **números del 1 al 50 con incrementos de 10 en 10**.

```{r}
seq(1, 50, 10)
```

- El primer elemento de la lista es un vector de caracteres de **tamaño 26** con las letras el abecedario.
- El segundo elemento de la lista es un vector numérico de **tamaño 10** con los números del 10 al 20.
- El tercer elemento de la lista es un vector lógico de **tamaño 5** que contiene 1 **FALSE** y 4 **TRUE**. Este vector evalúa si los elementos de la secuencia generada **seq(1, 50, 10)** son mayores que 10.

Los nombres de los elementos de la lista se pueden **ver** o **cambiar** con **names()**.

```{r}
names(lista) <- c("abecedario", "secuencia", "logica")
lista
```

También se pueden crear **listas de listas**.

```{r}
lista1 <- list(letras = letters,
               numeros = 10:20,
               logico = (seq(1, 50, 10) > 10))
lista1

lista2 <- list(frutas = c("pera", "limón", "manzana"),
               verduras = c("apio", "tomate", "lechuga"))
lista2

list(lista1, lista2)
```

## Matrices 

Las matrices son vectores de datos en forma tabular. Los datos tabulares consisten en **filas** y **columnas**.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\Matriz.png){width="25%"}

</center>

Las matrices solo contienen **un tipo de dato**.

Las matrices se crean con la función **matrix()**, que reorganiza los elementos de un vector atómico en forma de matriz.

El número de **filas** y **columnas** se especifica con los argumentos **nrow** y **ncol**, respectivamente. El tamaño de una matriz es igual a **nrow * ncol**.

```{r}
x <- matrix(1:10, nrow = 5, ncol = 2)
x
x <- matrix(1:10, nrow = 2, ncol = 5)
x
y <- matrix(11:25, nrow = 3, ncol = 5)
y

# Matriz de vector de caracteres
m <- matrix(letters, nrow = 2)
m

length(m)
```

Las **filas** se indican con **paréntesis cuadrados** que tienen el **número de la fila seguido por una coma ([1,], [2,], [3,])**, mientras que las **columnas** se indican con **paréntesis** cuadrados que son precedidos por una coma **([,1], [,2], [,3])**.

Si el tamaño de **nrow * ncol** es más grande que el tamaño del vector, se usará **reciclado** con una advertencia.

```{r}
x <- matrix(1:10, nrow = 2, ncol = 6)
x
```

Si el tamaño de **nrow * ncol** es **más pequeño** que el **tamaño del vector**, la construcción de la matriz se detendrá en las columnas y filas especificadas con una advertencia.

```{r}
y <- matrix(1:24, nrow = 3, ncol = 7)
y
```

**Por defecto**, las matrices se rellenan **por columna**. Para rellenar la matriz **por fila** se usa el argumento **byrow = TRUE**.

```{r}
y <- matrix(11:24, nrow = 3, ncol = 8)
y

y <- matrix(11:24, nrow = 3, ncol = 8, byrow  = TRUE)
y
```

#### Dimnames

El argumento **dimnames** controla los nombres de las filas y columnas.

Dimnames toma dos vectores, el primero son los **nombres de las filas**, y el segundo son los **nombres de las columnas**.

**Ejemplo:** fijar los nombres de las filas y columnas.

```{r}
y <- matrix(1:24, nrow = 3, ncol = 8,
            dimnames = list(c("fila1", "fila2", "fila3"),
                            c("columna1", "columna2", "columna3", "columna4", 
                              "columna5", "columna6", "columna7", "columna8")))
y
```

Para **cambiar los nombres** de las **filas** y **nombres de las columnas** de la matriz se usa la función **dimnames()**.

```{r}
dimnames(y) <- list(row = c("f1", "f2", "f3"),
                    columns = c("c1", "c2", "c3", "c4",
                                "c5", "c6", "c7", "c8"))
y
```

Para fijar los nombres de las columnas o filas **por separado**, se usa la función **colnames()** o **rownames()**.

**Ejemplo: colnames()**

```{r}
y <- matrix(1:24, nrow = 3, ncol = 8,
            dimnames = list(nombres_filas = c("fila1", "fila2", "fila3"),
                            nombres_columnas = c("columna1", "columna2", "columna3", "columna4", 
                                            "columna5", "columna6", "columna7", "columna8")))
colnames(y) <- c("c1", "c2", "c3", "c4",
                 "c5", "c6", "c7", "c8")
y
```

**Ejemplo: rownames()**

```{r}
y <- matrix(1:24, nrow = 3, ncol = 8,
            dimnames = list(nombres_filas = c("fila1", "fila2", "fila3"),
                            nombres_columnas = c("columna1", "columna2", "columna3", "columna4", 
                                            "columna5", "columna6", "columna7", "columna8")))
rownames(y) <- c("f1", "f2", "f3")
y
```

##### Función cbind()

La función **cbind()** permite crear matrices **combinando diferentes vectores por columna**.

```{r}
x <- 1:10
x

y <- 11:20
y

l <- 21:30
l

z <- cbind(x, y)
z

z <- cbind(x, y, l)
z
```

Las columnas se combinan en el **orden** que se agregaron a **cbind()**.

##### Función rbind()

La función **rbind()** permite crear matrices que combinan diferentes **vectores por fila**.

```{r}
z <- rbind(x, y)
z

z <- rbind(x, y, l)
z

z <- rbind(x, l, y)
z
```

Las filas se combinan en el orden que se agregan a la función **rbind()**. 

En los ejemplos anteriores, los vectores eran de igual tamaño. Se aplica **reciclaje** y se crea una advertencia si vectores más grandes **no son múltiplos de los vectores más cortos**.

```{r}
x <- 1:10
x

y <- 11:20
y

z <- rbind(1, x, y)
z

z <- rbind(1:3, x, y)
z

z <- rbind(1:5, x, y)
z
```

La alerta solo se produce cuando un vector de tamaño 3 se une con vectores de tamaño 10.

#### Combinación de matrices

Las funciones **rbind()** y **cbind()** se pueden usar para combinar **matrices** por filas o columnas.

```{r}
x <- matrix(1:10, ncol = 5, nrow = 2)
x

y <- matrix(61:70, ncol = 5, nrow = 2)
y

z <- rbind(x, y)
z

z <- cbind(x, y)
z
```

##### Función dim()

La función **dim()** permite obtener las **dimensiones de una matriz** (y dataframes), donde el **primer número** es el número de **filas** y el **segundo número** es el número de **columnas**.
```{r}
y <- matrix(1:24, nrow = 3, ncol = 8)
y
dim(y)
```

El **3** es el **número de filas** y **8** es el **número de columnas** en la matriz **y**.
La función **dim()** también puede crear una matriz a partir de un **vector** fijando estos dos números (número de filas, número de columnas).

```{r}
y <- 1:24
y

dim(y) <- c(3, 8)
y

dim(y) <- c(6, 4)
y
```

La matriz creada se llenó por columnas.

## Selección y modificación de valores

R tiene un sistema de notación que permite extraer valores de los objetos con el formato: **objeto[ , ]**.

Entre los paréntesis cuadrados hay dos índices separados por una **coma (“,”)**. Los índices determinan los valores a extraer.

- El primer índice subdivide **filas**.
- El segundo índice subdivide **columnas**.

Los índices se pueden crear con:

- Enteros positivos.
- Enteros negativos.
- Espacios en blanco.
- Nombres.
- Valores lógicos.

### Enteros positivos

Los enteros positivos se tratan con la notación **objeto/dataframe[fila, columna]**. Esto es, están basados en la posición de los elementos.


```{r}
x <- 1:10
x

# Extraer el primer elemento
x[1]

# Extraer el séptimo elemento
x[7]

# Extraer el tercer, quinto y sexto elemento
x[c(3, 5, 6)]

# Extraer los últmos cuatro elementos
x[c(7:10)]

datos <- data.frame(ID = c(1:5),
                    nombre = c("Diego", "Claudia", "Daniela", "Pedro", "Fernando"),
                    sexo = c("Hombre", "Mujer", "Mujer", "Hombre", "Hombre"),
                    depresion = runif(5, min = 1, max = 10))
datos

# Extraer el puntaje de depresión de la segunda fila del dataframe

datos[2, 4]

# Extraer el nombre y sexo de la cuarta fila del dataframe

datos[4, c(2, 3)]
```

Los resultados no modifican el objeto original, sino que corresponden a un nuevo objeto.

### Enteros negativos

Los enteros negativos **excluyen los elementos en la posición señalada**, y retienen los demás.

```{r}
x <- 1:10
x

# Extraer todos los elementos menos el primero
x[-1]

# Extraer todos los elementos menos el segundo
x[-2]

# Extraer todos los elementos menos el tercero y el quinto
x[-c(3, 5)]

x[c(-3, -5)]

# Extraer todos los elementos menos el tercero, quinto y sexto
x[-c(3, 5, 6)]

x[-c(3, 5:6)]

# Extraer todos los elementos menos los últimos cuatro
x[-7:-10]

x[c(-7:-10)]
```

Si se intenta **emparejar** un **entero negativo** con uno **positivo** en el **mismo índice** se obtiene un mensaje de error.

```{r}
vec <- 1:10
# vec[c(1, -1)]

# Entrega error
```

### Espacio en blanco

El espacio en blanco permite **extraer todos los valores de una dimensión (fila o columna)**. De este modo se pueden extraer filas o columnas completas de un dataframe:

```{r}
# Extraer todos los datos de la quinta fila del dataframe
datos[5, ]
```

### Nombres

Se pueden extraer elementos por su **nombre**, si el objeto los contiene. Esto permite extraer **columnas** de un dataframe.

```{r}
# Extraer columna depresion

datos[ , "depresion"]
```

### Valores lógicos

Los operadores lógicos comúnmente usados son:

- mayor que (>).
- menor que (<).
- mayor o igual que (>=).
- menor o igual que (<=).
- igual (==).
- no es igual (!=).

**Ejemplo:** extraer valores mayores que 50.

```{r}
x <- 1:100
y <- x[x > 50]
y
```

### Índices de carácter

Los índices de carácter extraen elementos de un **vector de caracteres**.

```{r}
x <- 1:12
x

names(x) <- month.abb
x

# Extraer mes de marzo
y <- x["Mar"]
y

# Extraer meses abril, junio y octubre
y <- x[c("Apr", "Jun", "Oct")]
y
```

### Operador %in%

El operador **%in%** permite extraer múltiples elementos al mismo tiempo.

```{r}
x <- 1:100
x

y <- x[x %in% c(10, 20, 30)]
y
```

Se extraen los elementos a la derecha del operador **%in%** (10, 20, 30) que están en el vector de la izquierda (**x**).

A **diferencia** de los **enteros positivos y negativos**, el operador **%in%** extrae el número real de elementos, y **no** los valores de una posición.

```{r}
x <- seq(0, 50, 5)
x

# Extraer los elementos de la posición 1, 5, 10 (con enteros positivos)

y <- x[x %in% c(1, 5, 10)]
y
```

Dado que el **1** no es un elemento de **x**, no se extrae al usar **%in%**.

### Modificación de valores en el lugar

Se pueden modificar valores **dentro** de un objeto de R.

Esto requiere describir el valor(res) a modificar, y luego usar el operador de asignación (**<-**) para re-escribir el valor.

**Ejemplo:** cambiar 0 por 1000.

```{r}
vec <- c(0, 0, 0, 0, 0, 0)
vec

# Seleccionar primer valor del vector
vec[1]

# Modificar el valor
vec[1] <- 1000
vec
```

Se pueden **reemplazar múltiples valores** a la vez:

```{r}
vector <- c(0, 0, 0, 0, 0)
vector

# Reemplazar los elementos de la primera, tercera y quinta posición por 1

vector[c(1, 3, 5)] <- c(1, 1, 1)
vector

# Sumar 9 a los dos últimos elementos (posiciones 4 y 5)

vector[c(4, 5)] <- vector[c(4, 5)] + 9
vector
```

De este modo se pueden **agregar** nuevas **columnas** a un dataframe:

```{r}
datos

x <- 80:84

datos$nuevacolumna <- x
datos
```

De manera similar, se pueden **remover** columnas de un dataframe con **NULL**.

```{r}
datos$depresion <- NULL
datos
```

# Visualización I: Introducción a ggplot2

**ggplot2** es un paquete del tidyverse el cual permite producir gráficos que, a diferencia de la mayoría de otros paquetes gráficos, tiene una gramática subyacente. Esta gramática, basada en la Gramática de los Gráficos (Wilkinson, 2005), engloba un conjunto de componentes independientes que se pueden establecer de diferentes maneras. Esto permite no solo crear gráficos predefinidos, sino también **gráficos personalizados** que se ajustan a distintas situaciones.


**ggplot2** busca establecer la estructura lógica de un gráfico, donde los códigos especifican conexiones entre las variables y las propiedades del gráfico (colores, puntos o formas). Estas **conexiones entre los datos y el gráfico** se denominan **mapeos estéticos o estéticas**.

En **ggplot2** los gráficos se crean con la función **ggplot()**.

Lo primero que se necesita es especificar el **objeto con los datos** y el modo en que las variables en los datos están **lógicamente mapeadas en estéticas** del gráfico.

Luego, sobre el resultado del mapeo, se especifica el **tipo de gráfico** (barras, histograma, dispersión, etc.). El tipo de gráfico se denomina **geom** (geometría). Por ejemplo, **geom_point()** crea diagramas de dispersión.

La información del mapeo y el geom se combina sumándolas con el símbolo **+**.

Un mapeo y geom son suficientes para producir un gráfico usando la configuración **por defecto** de ggplot2.

## Mapeos para vincular datos a elementos visuales

- El primer paso al crear un gráfico es asignar a un objeto (**p**) la definición de los **datos** y el **mapeo** dentro de **ggplot()**.

- Luego se escoge un **geom()** que se suma a **p**.

- El último paso es **controlar detalles finos** del gráfico (escalas, títulos o etiquetas).

Para ejemplificar lo anterior se usará el dataset **gapminder** de la librería **gapminder**.

```{r}

# install.packages("gapminder")

library(ggplot2)
library(gapminder)

gapminder
```

Se graficará la relación entre la **expectativa de vida (lifeExp)** y el **producto interno bruto per capita (gdpPercap)** para todos los años por país en los datos.

Primero se necesita especificar los datos (**gapminder**) con el argumento **data**, y determinar las variables de los datos que se representarán por medio de elementos visuales (**mapeo**). Los mapeos se realizan dentro la función **aes()** con el argumento **mapping**.

```{r}
# Datos y mapeo
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))
```

La función **aes()** indica que la variable del **eje x** será **gdpPercap**, y la variable del **eje y** será **lifeExp**. No es necesario especificar el dataset del que provienen las variables debido a que ya se hizo en el argumento **data**.

También se pueden agregar otros mapeos estéticos como **color, forma, tamaño, o tipo de línea**.

Nota que un mapeo **no se refiere a los colores o formas específicas** que estarán en el gráfico, sino a las **variables que se representarán con elementos visuales** (color, forma, puntos, etc.).

Si solo tipeamos **p** en la consola, el resultado será el siguiente:

```{r}
p
```

Solo se grafica el mapeo sin más información, debido a que **no se ha especificado el tipo de gráfico**. Esto requiere agregar una **capa (layer)** al gráfico usando alguna **geom_**. Se utiliza **geom_point()** para crear un diagrama de dispersión.

```{r}
p + geom_point()
```

## Creación de gráficos capa por capa

El proceso de creación de gráficos con **ggplot()** se puede resumir de la siguiente forma:

1. Definir el archivo de datos con el argumento **data**.
2. Definir los mapeos con el argumento **mapping = aes()**.

Asignar los resultados de los pasos anteriores a un objeto llamado **p**.

3. Determinar el tipo de gráfico con la función **geom_**.
4. Agregar capas de **geoms** sumándolas al objeto **p**.
5. Agregar información adicional para ajustar escalas, etiquetas, o títulos.

Por defecto, sistema de coordenadas de **ggplot()** es el **cartesiano**, un plano definido por un **eje x** y un **eje y**.

El proceso de agregar capas al gráfico es **aditivo**, lo que permite monitorear su creación pieza por pieza.

Se prueba una **geom_** diferente para el gráfico.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_smooth()
```

Como se observa, los geoms no solo agregan datos al gráfico, sino que también pueden hacer **cálculos**. Aquí, **geom_smooth()** calculó una función suave. El área sombreada corresponde al error estándar.

Si se necesita ver los puntos de los datos y la línea al mismo tiempo, simplemente se agrega **geom_point** de nuevo.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point() + 
    geom_smooth()
```

La consola informa que la función **geom_smooth()** usó el método **gam**, que ajusta un modelo generalizado aditivo.

**geom_smooth()** permite otros modelos, por ejemplo, un modelo lineal (**method = “lm”**).

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point() + 
    geom_smooth(method = "lm")
```

Podemos transformar la escala del **eje x** a una escala logarítmica. Para esto usamos la función **scale_x_log10()** que establece la escala del **eje x** a una **base de logaritmo 10**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point() + 
    geom_smooth(method = "gam") + 
    scale_x_log10()
```

**ggplot()** no cambia el dataframe. La escala del **eje x** se modifica antes de agregar el suavizador.

Adicionalmente, se pueden agregar etiquetas a los ejes. Por ejemplo, se puede cambiar la notación científica del eje x a los valores en dólar. Las funciones **scale_** controlan las etiquetas.

El paquete **scales** contiene diferentes formatos para las etiquetas.

```{r}

# install.packages("scales")

library(scales)

p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point() +
    geom_smooth(method = "gam") +
    scale_x_log10(labels = scales::dollar)
```

## Mapeando estéticas en vez de fijarlas

El **mapeo estético** especifica que una variable será expresada por uno de los elementos visuales disponibles (tamaño, color, forma, etc.).

Considere el siguiente mapeo estético.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp,
                          color = continent))
```

Este código hace que la variable **continent** sea representada por medio de la propiedad **color**. **No determina un color específico**, sino la variable que será expresada por medio de color.

El color específico de los puntos **no depende del mapeo**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp,
                          color = "purple"))

p + geom_point() + 
    geom_smooth(method = "loess") + 
    scale_x_log10()
```

El gráfico que resulta de escribir el nombre de un color en el mapeo de color es raro. Produce una leyenda que dice “purple” cuando los puntos son rojos.

Lo anterior ocurre porque **aes()** está indicando el mapeo de una variable que **no existe en los datos (purple)** al color. En consecuencia, ggplot crea una nueva columna (variable) con el valor **purple** en todas las filas, llevando a la leyenda generada. El gráfico muestra los puntos que caen dentro de la **categoría purple** (todos) usando el color rojo.

La función **aes()** solo establece el **mapeo**. Para fijar una propiedad (ej. color específico de los puntos) se modifica la función **geom_** fuera de **mapping = aes()**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point(color = "purple") + 
    geom_smooth(method = "loess") +
    scale_x_log10()
```

La función **geom_point()** puede tomar un argumento de **color**, donde R reconoce el color **“purple”**. Este **no es un mapeo estético** para definir la estructura del gráfico. El color purpura no representa (mapea) una variable de los datos.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point(alpha = 0.3) +
    geom_smooth(color = "orange", 
                se = FALSE,
                linewidth = 2,
                method = "lm") + 
    scale_x_log10()
```

Las funciones **geom_** pueden tomar argumentos que afectan la **apariencia** del gráfico **sin alterar el mapeo estético**. Estos argumentos nunca irán en la función **aes()**.

En **geom_smooth()** se puede fijar el color de la línea con **color**, el tamaño de la línea con **linewidth**, y remover la sombra del error estándar con **se = FALSE**.

En **geom_point()** se puede fijar la transparencia de los puntos con el argumento **alpha (0 = invisible a 1 = completamente opaco)**. Un alpha intermedio puede permitir visualizar la **superposición de puntos** en el gráfico, esto es, la concentración de las observaciones.

También podemos agregar **etiquetas** para los ejes, notas, títulos y subtítulos con la función **labs()**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))
                   
p + geom_point(alpha = 0.3) +
    geom_smooth(method = "gam") +
    scale_x_log10(labels = scales::dollar) +
    labs(x = "PIB per capita", 
         y = "Expectativa de vida en años",
         title = "Crecimiento económico y expectativa de vida",
         subtitle = "Los puntos son años por país",
         caption = "Fuente: Gapminder.")
```

Se puede mapear una variable a la estética **color**.

Se crea un gráfico donde el **color** de los puntos denota las **categorías de continent**. Por defecto, ggplot genera una leyenda con las claves de los colores. Adicionalmente, en lugar de solo una línea suave, ahora habrá cinco líneas suaves, una para cada valor de continent.

Esto requiere fijar el **mapeo estético** de **color** en el objeto **p**. Los **mapeos que se establecen directamente en ggplot() aplican para todas las geom_**. Por lo tanto, se obtienen puntos y suavizadores coloreados según el continente.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp,
                          color = continent))

p + geom_point() + 
    geom_smooth(method = "loess") + 
    scale_x_log10() +
    theme_bw()
```

Es conveniente agregar el **color de las líneas** a la **sombra de los errores estándar**. El color del error estándar se controla con la estética **fill**.

Mientras que la estética **color** afecta las **líneas** y **puntos**, **fill** afecta el relleno de barras, polígonos y, en este caso, el interior de los errores estándar.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp,
                          color = continent, 
                          fill = continent))

p + geom_point() + 
    geom_smooth(method = "loess") + 
    scale_x_log10() +
    theme_bw()
```

La apariencia del gráfico mejora si las estéticas de **color** y **fill** coinciden.

## Las estéticas se pueden mapear por geom

Por defecto, los mapeos declarados en la función **ggplot()** aplicarán a todos los **geom_**.

Esto se puede cambiar especificando diferentes estéticas dentro de cada **geom_**. Para esto se usa el mismo comando **mapping = aes()** dentro de las funciones **geom_**, indicando los mapeos que queremos dentro de cada una.

Así, se puede obtener el gráfico anterior con el siguiente código.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))

p + geom_point(mapping = aes(color = continent)) + 
    geom_smooth(mapping = aes(color = continent, 
                              fill = continent), 
                method = "loess") + 
    scale_x_log10() +
    theme_bw()
```

También se pueden **mapear variables continuas** a la estética **color**.

Por ejemplo, se puede mapear el **logaritmo de la población por año de cada país (pop)** a **color**. Con esto, **ggplot** produce una **escala gradiente** que es **continua**, aunque está marcada por **intervalos** en la leyenda. No obstante, a veces es más efectivo discretizar la variable continua antes de mapearla, pero siempre es recomendable revisar primero su forma continua.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))
                   
p + geom_point(mapping = aes(color = log(pop))) + 
    scale_x_log10() +
    theme_bw()
```

## Datos agrupados y la estética “group”

Se utilizan los datos **gapminder** para graficar la trayectoria de expectativa de vida de cada país a través del tiempo. Se mapea **year** al **eje x**, y **lifeExp** al **eje y**.

**geom_line** establece líneas que conectan las observaciones en el orden de la variable del **eje x**. Sin embargo, el resultado de solo agregar **geom_line** no es informativo.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = year, 
                          y = gdpPercap))

p + geom_line()
```

La razón es que no se ha definido la variable de agrupación (**country**) en **ggplot()**. Esta debe ser mapeada dentro de la estética **group** en **geom_line**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = year, 
                          y = gdpPercap))

p + geom_line(aes(group = country))
```

Ahora cada línea representa la trayectoria de un país específico a través del tiempo.

La estética **group** es útil cuando la información de la agrupación **no está** en las variables mapeadas.

## Facetas para hacer múltiples gráficos pequeños

Es posible crear un **panel separado** para cada valor de una **tercera variable**. Estos se denominan **facetas**. Las facetas no son una **geom**, sino una manera de organizar las **geoms**.

Se usa **facet_wrap()** para dividir el gráfico por **continent**.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = year, 
                          y = gdpPercap))

p + geom_line(aes(group = country)) + 
    facet_wrap(~continent)
```

Cada faceta tiene su respectiva etiqueta en la parte superior.

Si se incluyen más **geoms**, estas se cargarán dentro de cada faceta.

La función **ncol()** de **facet_wrap()** controla el **número de columnas** de las facetas. Debido a que solo hay 5 continentes, se ajusta el gráfico para alinear las facetas en una sola fila. También se agrega un suavizador y se cambia el color de las líneas por país a gris.

```{r}
p <- ggplot(data = gapminder, 
            mapping = aes(x = year, 
                          y = gdpPercap))

p + geom_line(color = "gray70", 
              aes(group = country)) +
    geom_smooth(linewidth = 1.1, 
                method = "loess", 
                se = FALSE) +
    scale_y_log10(labels=scales::dollar) +
    facet_wrap(~ continent, ncol = 5) +
    labs(x = "Año",
         y = "PIB per capita",
         title = "PIB per capita en los cinco continentes")
```

Para hacer facetas de acuerdo a la clasificación cruzada de dos variables categóricas se usa **facet_grid()**. Para ilustrar esto se usa el **dataset gss_sm** (librería **socviz**) sobre una encuesta social.

Se crea un diagrama de dispersión sobre la relación entre la edad y el número de hijos incluyendo un suavizador, y faceteando esta relación por el sexo y raza del participante: **facet_grid(sex ~ race)**.

```{r}
library(socviz)

p <- ggplot(data = gss_sm,
            mapping = aes(x = age, 
                          y = childs))

p + geom_point(alpha = 0.2) +
    geom_smooth() +
    facet_grid(sex ~ race)
```

## Histogramas y gráficos de densidad

Un histograma resume una variable continua mediante **segmentos** o **uniones** (barras), y contando las observaciones dentro de cada unión. La geometría para histograma es **geom_histogram()**.

Se ilustra la elaboración de un histograma usando los datos **midwest**, que contiene información de varios condados de Estados Unidos. Los condados varían en **tamaño** (millas cuadradas). Se usa un histograma para mostrar la distribución de las áreas geográficas. Debido a que se resume una variable continua, es necesario dividir las observaciones en **grupos** o **intervalos (bins)** y luego contarlas.

```{r}
p <- ggplot(data = midwest, 
            mapping = aes(x = area))

p + geom_histogram()
```

Por defecto, se usan **30** bins para elaborar el histograma. Esta configuración se puede cambiar con el argumento bins de **geom_histogram**.

```{r}
p <- ggplot(data = midwest, 
            mapping = aes(x = area))

p + geom_histogram(bins = 10)
```

También se pueden comparar distribuciones usando histogramas con diferente **fill**.

```{r}
# Se delimitan dos estados

oh_wi <- c("OH", "WI")

p <- ggplot(data = subset(midwest, 
                          subset = state %in% oh_wi),
            mapping = aes(x = percollege, 
                          fill = state))

p + geom_histogram(alpha = 0.4, 
                   bins = 20)
```

Para crear el gráfico primero se crea un **vector de caracteres** con 2 elementos, **“OH”**, y **“WI”**. Luego se usa la función **subset()** para filtrar los datos seleccionando solo aquellas columnas donde el nombre de **state** se encuentra en este vector. El operador **%in%** permite filtrar uno o más términos en una variable cuando se usa **subset()**.

Otra forma de resumir una variable continua es con **gráficos de densidad de kernel** empleando **geom_density()**. Estos muestran la distribución subyacente de la variable.

```{r}
p <- ggplot(data = midwest, 
            mapping = aes(x = area))

p + geom_density()
```

Se pueden comparar distribuciones de densidad de acuerdo a una tercera variable de agrupación mapeándola a **color (línea)** y **fill (relleno)**, respectivamente.

```{r}
p <- ggplot(data = midwest, 
            mapping = aes(x = area, 
                          fill = state,
                          color = state))

p + geom_density(alpha = 0.3)
```

## Gráficos de barras

### Gráfico de barras simple

Para crear gráficos de barrras se usa **geom_bar()**.

Los gráficos de barras son útiles para visualizar los conteos y porcentajes de una tabla de resumen.

El **dataset titanic (socviz)** consiste en una tabla de resumen sobre el conteo de sobrevivientes del titanic por sexo.

```{r}
titanic
```

Algunas geoms activan implícitamente funciones **stat_** que realizan cálculos en base a configuraciones por defecto. Debido a que la tabla ya contiene los porcentajes, no es necesario que **ggplot()** realice el **conteo** a través de la función **stat_** que **geom_bar()** llama por defecto.

Para hacer que **geom_bar()** no realice operaciones sobre la variable antes de graficarla, se usa **stat = ‘identity’**.

Debido a lo anterior, **ggplot()** tiene una geometría similar a **geom_bar()** que es **geom_col()**, la cual es igual pero asume que **stat = “identity”**. Esta es útil cuando no se necesitan cálculos al elaborar el gráfico.

Se crea un gráfico de barras para los porcentajes de supervivencia del titanic.

```{r}
p <- ggplot(data = titanic, 
            mapping = aes(x = fate, 
                          y = percent))

p + geom_bar(stat = "identity", 
             alpha = 0.9) + 
    theme_bw()
```

Se crea el mismo gráfico con **geom_col()**.

```{r}
p <- ggplot(data = titanic, 
            mapping = aes(x = fate, 
                          y = percent))

p + geom_col(alpha = 0.9) + 
    theme_bw()
```

### Gráfico de barras agrupadas

#### Preparación de los datos

Las **geoms** suelen resumir los datos de forma **automática**. Sin embargo, es mejor dejar los datos en el formato correcto antes de graficarlos. Lo anterior se puede realizar con el paquete **dplyr**, el cual entrega herramientas para el manejo de datos en R.

Los datos de una tabla de contingencia se pueden resumir usando **frecuencias relativas por filas o columnas**. Si bien **geom_bar()** puede graficar frecuencias relativas, el gráfico que entrega por defecto en este caso es confuso, ya que no es claro si las frecuencias relativas se calcularon por fila, columna o en general.

Por lo tanto, es recomendable calcular la **tabla de frecuencias primero y luego graficarla**, puesto que permite chequear que no se han cometido errores.

Utilizando el dataset **gss_sm** de la librería **socviz**, se graficarán las frecuencias relativas de cada religión dentro de regiones específicas. Esto requiere disponer de una **tabla con los porcentajes de preferencia religiosa agrupados por región**.

Para crear la tabla primero se resumen los datos individuales de un dataframe común en una tabla con el **conteo de cada preferencia religiosa agrupada por región** (de los sujetos de una región, la cantidad en cada afiliación religiosa). Luego los conteos se convierten a **porcentajes utilizando como denominador el número total de participantes en cada región**. Lo anterior se puede realizar con dplyr, donde **group()** permite agrupar los datos de religión por región; **summarize()** permite calcular los conteos **n()**; y **mutate()** permite calcular los porcentajes agrupados.

Se crea una tabla llamada **reli_by_region**.

```{r}
library(dplyr)

reli_by_region <- gss_sm %>%
                            group_by(bigregion, religion) %>%
                            summarize(N = n()) %>%
                            mutate(rel_freq = N / sum(N), 
                                   pct = round((rel_freq*100), 0))
```

La función **round()** permite redondear al entero más cercano.

Cada función usada para crear una nueva variable dentro de **summarize()**, como **mean()**, **sd()**, o **n()**, será aplicada según el primer nivel de agrupamiento. Los niveles de agrupamiento se nombran de izquierda a derecha dentro de **group_by()**, desde el más externo al más interno.

Así, la función **summarize(N = n())** cuenta el número de observaciones por cada valor de **religion** dentro de **biregion**, y los indica en una nueva variable llamada **N**.

De este modo, el código toma el dataframe **gss_sm** (2.867 filas y 32 columnas) y lo transforma en **reli_by_region**, una tabla de resumen con 24 filas y 5 columnas.

```{r}
print(reli_by_region, n = 24)
```

Una manera de chequear que la tabla se creó correctamente es verificar que los valores de **pct** vinculados a religión **sumen 100 dentro de cada región**.

```{r}
reli_by_region %>% group_by(bigregion) %>% 
                   summarize(total = sum(pct))
```

El resultado es correcto aunque puede no ser exacto debido a error de redondeo.

#### Creación del gráfico de barras agrupadas

Dado que se trabaja directamente con los valores de porcentaje generados en la tabla anterior, se puede usar **geom_col()** en lugar de **geom_bar()**.

```{r}
p <- ggplot(reli_by_region, aes(x = bigregion, 
                                y = pct, 
                                fill = religion))

p + geom_col(position = "dodge2") +
    labs(x = "Region", 
         y = "Percent", 
         fill = "Religion") +
    theme(legend.position = "bottom")
```

La **geom_col()** tiene el argumento **position = dodge2** que separa las barras (a diferencia de **dodge** que las junta).

Los valores del gráfico de barras son equivalentes a los porcentajes agrupados de la tabla **reli_by_region**. Las afiliaciones religiosas **suman 100** dentro de cada región. Sin embargo, la figura está cargada de información (demasiadas barras). Para solucionar este problema se pueden usar **facetas**, lo que facilita la lectura debido a que elimina la necesidad de una leyenda.

```{r}
p <- ggplot(reli_by_region, aes(x = religion, 
                                y = pct, 
                                fill = religion))

p + geom_col(position = "dodge2") +
    labs(x = NULL, 
         y = "Percent", 
         fill = "Religion") +
    guides(fill = "none") +
    facet_grid(~ bigregion)
```

Al establecer las facetas se repiten las etiquetas y se vuelven ilegibles. Esto se puede compensar invirtiendo los ejes del gráfico con **coord_flip()**.

```{r}
p <- ggplot(reli_by_region, aes(x = religion, 
                                y = pct, 
                                fill = religion))

p + geom_col(position = "dodge2") +
    labs(x = NULL, 
         y = "Percent", 
         fill = "Religion") +
    guides(fill = "none") +
    coord_flip() +
    facet_grid(~ bigregion)
```

Es importante notar que coord_flip() no vuelve a mapear las variables a estéticas, **solo gira los ejes**.

Debido a que no se necesita una leyenda para entender los nombres de **religion**, esta se elimina con **x = NULL** en **labs()**.

## Diagrama de cajas y bigotes

El dataset **organdata (socviz)** contiene información sobre la donación de órganos para trasplante de 17 países OECD. Se analiza la tasa de obtención de órganos (**donors**), esto es, el número de órganos humanos obtenidos de cadáveres de donantes para el uso de operaciones de trasplante. El dataset presenta datos perdidos (**NA**).

Se analizará la variación anual a nivel de los países en la tasa de donantes con **geom_boxplot()**.

Al igual que **geom_bar()**, **geom_boxplot()** calcula por defecto el conteo de observaciones para la variable que se mapeó al **eje x**. La función **stat_boxplot()** asociada a **geom_boxplot()** calcula los estadísticos que permiten dibujar las cajas y bigotes.

Se crean diagramas de cajas y bigotes para la variable continua **donors** según la variable de agrupación **country**.

```{r}
p <- ggplot(data = organdata, 
            mapping = aes(x = country, 
                          y = donors))

p + geom_boxplot()
```

El gráfico muestra **dos problemas**. El **primero** es que las etiquetas del **eje x** se superponen. Esto se puede solucionar girando los ejes con **coord_flip()**.

```{r}
p <- ggplot(data = organdata, 
            mapping = aes(x = country, 
                          y = donors))

p + geom_boxplot() + 
    coord_flip()
```

El **segundo problema** que afecta a este gráfico es que los datos **no están ordenados**. Es recomendable que los países estén ordenados según su tasa de donación.

Esto se puede solucionar reordenando la variable **country** según el promedio de **donors** con la función **reorder()**, donde:

- El **primer argumento** es la **variable categórica** que se quiere ordenar (**country**).
- El **segundo argumento** es la variable por la que se quiere reordenar (**donors**).
- El **tercer argumento** (opcional) es la función que se usará como **estadístico de resumen** para ordenar. Por defecto, **reorder()** reordenará las categorías de la primera variable (**country**) por el **promedio** de la segunda. Sin embargo, también se puede usar otra función para reordenar (ej. **median** o **sd**).

R arrojará un error al usar la función **mean()** por defecto si hay datos perdidos (**NA**) en la variable de la que se obtienen los promedios. Por lo tanto, se deben **remover los valores perdidos al calcular el promedio** con el argumento **na.rm = TRUE** en **reorder()**.

Debido a que se está reordenando la variable mapeada al **eje x**, se usa **reorder()** en ese punto del código.

```{r}
p <- ggplot(data = organdata, 
            mapping = aes(x = reorder(country, 
                                      donors, 
                                      na.rm = TRUE), 
                          y = donors))

p + geom_boxplot() + 
    labs(x = NULL) + 
    coord_flip()
```

Debido a que es obvio que las categorías del **eje y** son países, se eliminó la etiqueta del **eje y** con **labs(x = NULL)**.

Los boxplots pueden tomar mapeos estéticos de **color** y **fill** para otras variables.

```{r}
p <- ggplot(data = organdata,
            mapping = aes(x = reorder(country, 
                                      donors, 
                                      na.rm=TRUE),
                          y = donors, 
                          fill = world))

p + geom_boxplot() + 
      labs(x = NULL) +
      coord_flip() + 
      theme(legend.position = "bottom") # etiquetas en la parte inferior
```

## Gráfico de jitter

Si el **número de observaciones** dentro de cada categoría es relativamente **bajo**, se pueden mostrar directamente las observaciones individuales.

En el siguiente gráfico se mapea la variable **world** a **color (no a fill)**, ya que por defecto **geom_point()** grafica la **forma** como un atributo de **color (no el relleno)**.

```{r}
p <- ggplot(data = organdata,
            mapping = aes(x = reorder(country, 
                                      donors, 
                                      na.rm = TRUE),
                          y = donors, 
                          color = world))
p + geom_point() + 
    labs(x = NULL) +
    coord_flip() + 
    theme(legend.position = "bottom")
```

Al usar **geom_point()** de esta forma puede haber **superposición** de las observaciones. En estos casos, es más útil usar **geom_jitter()**, que funciona como **geom_point()**, pero desplaza levemente cada observación de manera aleatoria.

```{r}
p <- ggplot(data = organdata,
            mapping = aes(x = reorder(country, 
                                      donors, 
                                      na.rm=TRUE),
                          y = donors, color = world))

p + geom_jitter() + 
    labs(x = NULL) +
    coord_flip() + 
    theme(legend.position = "bottom")
```

La **cantidad de jitter** se controla con los argumentos **height** y **width** de la función **position_jitter()** dentro de **geom_jitter()**. Debido a que se realiza un resumen unidimensional, solo se necesita **width**.

```{r}
p <- ggplot(data = organdata,
                   mapping = aes(x = reorder(country, 
                                             donors, 
                                             na.rm=TRUE),
                                 y = donors, 
                                 color = world))

p + geom_jitter(position = position_jitter(width = 0.15)) +
    labs(x = NULL) + 
    coord_flip() + 
    theme(legend.position = "bottom")
```

## Gráfico de puntos Cleveland

### Preparación de los datos

El **jitter** también es útil al graficar una variable categórica que tiene **solo un dato** por categoría. Este tipo de gráfico se denomina **gráfico de puntos Cleveland**.

Se realizará un gráfico de puntos Cleveland del **promedio de la tasa de donación**.

Esto requiere resumir primero los datos con **dplyr**, agregando el dataframe a una tabla más pequeña de estadísticos de resumen por país.

Para hacer esta tarea se elige la variable a resumir (**donors**), y se usa **mean()** y **sd()** para calcular su promedio y desviación estándar según las variables de agrupación.

```{r}
by_country <- organdata %>% 
              group_by(consent_law, country) %>%
              summarize(donors_mean = mean(donors, 
                                           na.rm = TRUE),
                        donors_sd = sd(donors, 
                                       na.rm = TRUE))

by_country
```

En este código primero se agrupan los datos por **consent_law** y **country**. Luego se usa **summarize()** para crear dos nuevas variables, **donors_mean** y **donors_sd**, que corresponden al promedio y desviación estándar de donors de cada país, distinguiendo entre los países que tienen una ley de consentimiento informado o presumido para la donación de órganos.

**summarize()** hace sus cálculos en el nivel de agrupación más interno. En este caso, toma todas las observaciones por país, y luego calcula el promedio y desviación estándar solicitada.

En el nuevo dataframe, se retienen las variables especificadas en **group_by()**, se agregan las variables creadas con **summarize()**, y se eliminan todas las demás variables en el dataset original.

Los países son resumidos en **orden alfabético** dentro de **consent_law**, que es la variable de agrupación más externa en **group_by()**.

### Crear gráfico de puntos Cleveland

Con los datos resumidos según **país**, se crea un gráfico de puntos con **geom_point()**. Se usa **color** para **consent_law**.

```{r}
p <- ggplot(data = by_country,
            mapping = aes(x = donors_mean, 
                          y = reorder(country, 
                                      donors_mean),
                          color = consent_law))

p + geom_point(size = 3) +
      labs(x = "Donor Procurement Rate",
           y = "", 
           color = "Consent Law") +
           theme(legend.position = "bottom")
```

En lugar de colorear los puntos, se pueden usar **facetas**. Se puede usar **facet_wrap()** para dividir la variable **consent_law** en dos paneles, y luego **ranquear** los países por tasa de donación dentro de cada panel.

Sin embargo, hay dos problemas con este posible gráfico:

- Por defecto, **facet_wrap()** grafica los paneles de izquierda a derecha. Es más útil ordenarlos de manera **vertical** para comparar los dos grupos en la misma escala. Esto se corrige declarando que los paneles aparezcan en forma vertical especificando **1 columna** con el argumento **ncol = 1**.

- La lista de países aparecerá completa en ambos paneles, aunque solo la mitad de las filas de cada panel tendrán puntos. Esto se corrige permitiendo que la escala del **eje y sea libre** con el argumento **scales = “free_y”**.

```{r}
p <- ggplot(data = by_country,
            mapping = aes(x = donors_mean,
                          y = reorder(country, 
                                      donors_mean)))

p + geom_point(size = 3) +
    facet_wrap(~ consent_law, 
               scales = "free_y", 
                ncol = 1) +
    labs(x = "Donor Procurement Rate",
         y = "")
```

### Incluir la variabilidad

El gráfico de puntos Cleveland también puede incluir información sobre la varianza o error.

Con **geom_pointrange()**, ggplot puede mostrar la **estimación puntual** y un **rango** en torno a esta. En este caso, se usará la desviación estándar de la tasa de donación.

La función **geom_pointrange()** requiere más información que **geom_point()**, particularmente, el **rango de la línea a cada lado del punto**. Esto se define con los argumentos **ymax** e **ymin**.

Aquí, esto está dado por el valor de **y (donors_mean) más y menos su desviación estándar (donors_sd)**.

```{r}
p <- ggplot(data = by_country, 
            mapping = aes(x = reorder(country, 
                                      donors_mean), 
                          y = donors_mean))

p + geom_pointrange(mapping = aes(ymin = donors_mean - donors_sd,
                                  ymax = donors_mean + donors_sd)) +
    labs(x = "", 
         y = "Donor Procurement Rate") + 
    coord_flip()
```

## Escalas y guías

¿Cuáles son las diferencias entre las funciones **scale_**, **guides()** y **theme()**?, ¿Cuándo se usa una en lugar de la otra?, y, ¿Por qué hay diversas funciones **scale_**?

**Cada mapeo estético tiene una escala**. Para ajustar la manera en que se marca o gradúa la escala, se usa la función **scale_**.

Varias escalas vienen con una **leyenda** que facilita la interpretación del gráfico. Estas se denominan **guías** y se ajustan con la función **guides()**, que permite eliminar una leyenda o arreglar sus claves.

La **guía** entrega información sobre la escala, tal como en una leyenda o barra de color. Por lo tanto, es posible ajustar guías dentro de varias funciones **scale_**. Sin embargo, también es posible usar **guides()** directamente.

```{r}
p <- ggplot(data = organdata,
            mapping = aes(x = roads,
                          y = donors,
                          color = world))
p + geom_point()
```

Este gráfico tiene 3 mapeos estéticos. 

La variable **roads** está mapeada al **eje x**, **donors** al **eje y**, y **world** a **color**. 

Las escalas **x** e **y** son **continuas** y tienen varias marcas que orientan al lector sobre los valores de cada **eje**. 

La variable **world** se mapeó a **color**. Esta tiene una escala **discreta**. Toma uno de cuatro valores representados por un color diferente.

Además de **color**, los mapeos **fill**, **shape** y **size** tienen escalas que se pueden ajustar. 

Si se hubiese mapeado **world** a **shape**, las cuatro categorías se habrían representado con formas diferentes.

Las escalas de cada mapeo pueden tener **etiquetas, marcas en posiciones particulares, y colores o formas específicas**. Para ajustarlas, se usa alguna función **scale_**.

-	Un mapeo al **eje x** o **eje y** se puede definir a través de una escala especial, como la escala logarítmica.

- Un mapeo **color** o **fill** puede ser discreto como en el gráfico anterior, pero también puede ser una cantidad continua. Esta última se representa con un gradiente que va desde un valor bajo a uno alto.

Debido a que existen diferentes mapeos posibles y cada mapeo puede tener diferentes escalas, existen múltiples funciones **scale_** individuales. Cada función **scale**:

-	Comienza con **scale_**.
-	Luego el **mapeo** que aplica.
-	Y finalmente el **tipo de valor** que mostrará la escala.

Por ejemplo:

-	**scale_x_continuous()** controla la escala del **eje x** para variables **continuas**.
-	**scale_y_discrete()** ajusta la escala del **eje y** para variables **discretas**.
-	**scale_x_log10()** transforma un mapeo al **eje x** en una escala **logarítmica**.

La mayoría de las veces **ggplot2** establece por defecto las marcas de la escala en cada mapeo.

Si se mapea una variable continua a **x**, agregar **+ scale_x_continuous()** al gráfico sin argumentos no tendrá efecto. Sin embargo, agregar **+ scale_x_log10()** transformará la escala del eje debido a que se está modificando el tratamiento por defecto de las variables continuas.

Para cambiar las **etiquetas** o **marcas** de una escala, se necesita determinar qué tipo de escala es, y luego especificar los argumentos apropiados para la función de escala correspondiente.

**Ejemplo:** Cambiar la escala del **eje x** a una escala **log**, y las marcas del **eje y** junto con sus etiquetas.

```{r}
p <- ggplot(data = organdata,
            mapping = aes(x = roads, 
                          y = donors, 
                          color = world))

p + geom_point() + 
    scale_x_log10() + 
    scale_y_continuous(breaks = c(5, 15, 25), 
                       labels = c("Five", "Fifteen", "Twenty Five"))
```

Lo mismo aplica para los mapeos como **color** y **fill**. 

Cuando una escala produce una leyenda, se puede usar su función **scale_** para especificar las etiquetas de sus claves.

Sin embargo, para cambiar el **título de la leyenda** o de los **ejes**, se utiliza la función **labs()**.

```{r}
p <-  ggplot(data = organdata, 
             mapping = aes(x = roads, 
                           y = donors, 
                           color = world))

p + geom_point() + 
    scale_color_discrete(labels = c("Corporatist", 
                                    "Liberal", 
                                    "Social Democratic", 
                                    "Unclassified")) + 
    labs(x = "Road Deaths", 
         y = "Donor Procurement", 
         color = "Welfare State")
```

Para **mover la leyenda** a algún lugar específico se necesita la función **theme()**. Agregar **+ theme(legend.position = "top")** moverá la leyenda a la parte superior de la figura.

Finalmente, para eliminar la leyenda se agrega **+ guides(color = FALSE)**.

```{r}
p <- ggplot(data = organdata, 
            mapping = aes(x = roads, 
                          y = donors, 
                          color = world))

p + geom_point() + 
    labs(x = "Road Deaths", 
         y = "Donor Procurement") + 
    guides(color = "none")
```

## Temas

Los temas se relacionan con características del gráfico que no están vinculadas al mapeo establecido. Estas características abarcan el color de fondo, fuente de las etiquetas, ubicación de la leyenda, etc. 

Los temas se controlan con la función **theme()**.

Existen varios temas completos por defecto.

```{r}

# Por defecto 

p <- ggplot(data = gapminder, 
            mapping = aes(x = gdpPercap, 
                          y = lifeExp))
p + geom_point()

# Agregando un tema

p + geom_point() +
    theme_bw()

p + geom_point() +
    theme_linedraw()

p + geom_point() +
    theme_dark()

p + geom_point() +
    theme_minimal()

p + geom_point() +
    theme_classic()

p + geom_point() +
    theme_void()

p + geom_point() +
    theme_test()
```

## Paletas de color

Se pueden utilizar diferentes paletas de color predefinidas para los mapeos de un gráfico.

El paquete **RColorBrewer** entrega varias paletas de color, con opciones para escalas continuas y discretas.

<center>

![](C:\Users\jorge\Desktop\DOCENCIA\A. Taller Introducción a R para ciencias sociales y de la salud\SINTESIS BOOKDOWN\BOOKDOWN2\paletas1.png){width="50%"}

</center>

```{r}

# install.packages("RColorBrewer")

library(RColorBrewer)

p <- ggplot(data = organdata,
            mapping = aes(x = reorder(country, 
                                      donors, 
                                      na.rm=TRUE),
                          y = donors, 
                          fill = world))

p + geom_boxplot() + 
    labs(x = NULL) +
    coord_flip() + 
    theme(legend.position = "bottom") +
    scale_fill_brewer(palette = "Dark2")
```

# Visualización II: Aplicaciones

En el siguiente documento se ilustra la creación diferentes visualizaciones de datos con **ggplot2**. Para ello, se utiliza el dataset **datospss.sav**.

```{r}

library(haven)

datosSPSS <- read_sav("datosspss.sav")

# Libro de códigos

library(readxl)

codigos <- read_xlsx("codigos.xlsx")

print(codigos, n = 30)

library(ggplot2)
```

## Histogramas

### Histograma univariado

Se visualizarán los datos de la variable **felicidad**, que tiene un rango de 1 a 5 puntos.

```{r}
summary(datosSPSS$felicidad)
```

El histograma por defecto que genera ggplot es:

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram()
```

El gráfico se puede mejorar de diferentes formas.

Para cambiar el color de las barras de **gris** a **rojo oscuro**, se utiliza el argumento **fill = "red4"** dentro de **geom_histogram()**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram(fill = "red4")
```

Personalmente, no me gusta el fondo gris, así que lo quitaré estableciendo el **tema blanco y negro**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram(fill = "red4") + 
    theme_bw()
```

Las etiquetas de los ejes no son muy informativas, e incluso una está en inglés ("count"). Para modificarlas, se utiliza la función **labs()**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram(fill = "red4") + 
    theme_bw() + 
    labs(x = "Puntaje de felicidad",
         y = "n")
```

Para examinar de manera más detallada las frecuencias puede ser necesario un mayor **número de marcas** en el **eje y**. Estas marcas se controlan con la función **scale_y_continuous()**. En este caso, se establecen marcas cada 50 casos.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram(fill = "red4") + 
    theme_bw() + 
    labs(x = "Puntaje de felicidad",
         y = "n") + 
    scale_y_continuous(breaks = seq(0, 500, by = 50))
```

Por último, puede ser útil estéticamente delinear los bordes de las barras, los cuales se controlan con el argumento **color** dentro de **geom_histogram()**. Aquí, se establece el color negro para los bordes.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))

p + geom_histogram(fill = "red4",
                   color = "black") + 
    theme_bw() + 
    labs(x = "Puntaje de felicidad",
         y = "n") + 
    scale_y_continuous(breaks = seq(0, 500, by = 50))
```

### Histograma bivariado

#### Barras superpuestas

Para examinar simultáneamente la distribución de una variable numérica entre dos grupos diferentes, es posible crear un histograma con barras superpuestas para cada grupo.

Esto requiere primero transformar la variable de agrupación en factor.

```{r}
datosSPSS$sexo <- factor(datosSPSS$sexo)
```

El código de este tipo de gráfico requiere especificar la **variable de agrupación** ("sexo") en el argumento **fill** del mapeo general.

La apariencia por defecto de este gráfico es:

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram()
```

Este tipo de visualización se puede ver beneficiada por la transparencia de las barras, que se controla con el argumento **alpha** dentro de **geom_histogram()**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram(alpha = 0.7)
```

Para eliminar el fondo gris se usa el **tema blanco y negro**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram(alpha = 0.7) + 
    theme_bw()
```

Se pueden ajustar las etiquetas y valores de los ejes como antes.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram(alpha = 0.7) + 
    theme_bw() +
    labs(x = "Puntaje de felicidad", y = "n") +
    scale_y_continuous(breaks = seq(0, 500, by = 50))
```

Finalmente, es necesario modificar la guía para que el gráfico sea interpretable. 

El **título de la guía** se controla con el argumento **fill** dentro de **labs()**, mientras que las etiquetas de **1** y **2** se modifican con el argumento **labels** de la función **scale_fill_discrete()**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram(alpha = 0.7) + 
    theme_bw() +
    labs(x = "Puntaje de felicidad", y = "n", fill = "Sexo") +
    scale_y_continuous(breaks = seq(0, 500, by = 50)) +
    scale_fill_discrete(labels = c("Hombre", "Mujer"))
```

El color del borde de las barras se puede establecer como se realizó previamente.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad,
                          fill = sexo))

p + geom_histogram(alpha = 0.7, 
                   color = "black") + 
    theme_bw() +
    labs(x = "Puntaje de felicidad", y = "n", fill = "Sexo") +
    scale_y_continuous(breaks = seq(0, 500, by = 50)) +
    scale_fill_discrete(labels = c("Hombre", "Mujer"))
```

#### Facetas

Otra manera de examinar la distribución de una variable numérica entre dos grupos es utilizar facetas para visualizar un histograma separado en cada grupo.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))
  
p + geom_histogram() +
    facet_wrap(~ sexo)
```

Se pueden implementar cambios en la apariencia del gráfico como antes.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))
  
p + geom_histogram(fill = "red4",
                   color = "black") +
    facet_wrap(~ sexo) +
    theme_bw() +
    labs(x = "Puntaje de felicidad", 
         y = "n") + 
    scale_y_continuous(breaks = seq(0, 300, by = 50))
```

Para cambiar los valores de **1** y **2** a **Hombre** y **Mujer**, respectivamente, se necesita recodificar la variable **sexo**.

```{r}
library(dplyr)

datosSPSS <- datosSPSS %>% 
             mutate(sexo = case_when(sexo == 1 ~ "Hombre",
                                     sexo == 2 ~ "Mujer"))

p <- ggplot(data = datosSPSS,
            mapping = aes(x = felicidad))
  
p + geom_histogram(fill = "red4",
                   color = "black") +
    facet_wrap(~ sexo) +
    theme_bw() +
    labs(x = "Puntaje de felicidad", 
         y = "n") + 
    scale_y_continuous(breaks = seq(0, 300, by = 50))
```

## Gráfico de densidad

### Gráfico de densidad simple

Se creará un gráfico de densidad para los puntajes totales de depresión (**total_depre**).

```{r}
datosSPSS <- datosSPSS %>% mutate(total_depre = depre1 + depre2 + depre3 + depre4)
```

Por defecto, el gráfico es.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = total_depre))

p + geom_density()
```

Se puede mejorar el gráfico agregando un color a **fill**, etiquetas para los ejes, y cambiando el tema a **blanco y negro**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = total_depre))

p + geom_density(fill = "gray80") +
    labs(x = "Puntaje total de depresión",
         y = "Densidad") +
    theme_bw()
```

### Gráfico de densidad agrupado

Se utilizará un gráfico de densidad agrupado para examinar si la distribución de **total_depre** es diferente entre hombres y mujeres.

Para detectar la superposición de las distribuciones, se utiliza transparencia con el argumento **alpha**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = total_depre,
                          fill = sexo,
                          color = sexo))

p + geom_density(alpha = 0.3)
```

Agregando algunos detalles, el gráfico resultante es el siguiente.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = total_depre,
                          fill = sexo,
                          color = sexo))

p + geom_density(alpha = 0.3) +
    labs(x = "Puntaje total de depresión",
         y = "Densidad",
         fill = "Sexo") +
    guides(color = "none") +
    theme_bw()
```

La especificación de **guides(color = "none")** permite eliminar la segunda leyenda que se genera para el mapeo de **color**, la cual es redundante debido a que tiene la misma interpretación de la leyenda de **fill**.

## Gráfico de barras

### Gráfico de barras simple

Se creará un gráfico de barras simple para el consumo de alcohol. 

Primero, se recodifica la variable de consumo de alcohol para que sus categorías sean "Sí" y "No". Luego, se recodifica como factor.

```{r}
datosSPSS <- datosSPSS %>% 
             mutate(sustan1 = case_when(sustan1 == 1 ~ "Sí",
                                        sustan1 == 2 ~ "No"))

datosSPSS$sustan1 <- factor(datosSPSS$sustan1)
```

El gráfico de barras por defecto es el siguiente.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sustan1))

p + geom_bar()
```

Se agregan algunos cambios estéticos al gráfico.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sustan1,
                          fill = sustan1))

p + geom_bar(color = "black") +
    labs(x = "Consumo de alcohol",
         y = "n") + 
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    theme_bw()
```

#### Calcular porcentajes 

Interpretar el gráfico de barras simple en términos de porcentajes no es una tarea tan sencilla.

Primero se deben calcular los porcentajes a través de mutaciones agrupadas. En este caso, estas mutaciones se asignan al objeto **frecuencias**.

```{r}
frecuencias <- datosSPSS %>% group_by(sustan1) %>% 
                             summarize(N = n()) %>% 
                             mutate(frecuencia_relativa = N / sum(N), 
                             porcentaje = round((frecuencia_relativa*100), 0))

frecuencias
```

Luego, se crea un gráfico especificando en el mapeo la variable del **eje x (sustan1)** y en el **eje y la columna con los porcentajes**, que se encuentra en el objeto **frecuencias**.

```{r}
p <- ggplot(data = frecuencias,
            mapping = aes(x = sustan1,
                          y = porcentaje))
```

**geom_bar()** realiza cálculos de manera automática para obtener el conteo de observaciones por grupo. Dado que este cálculo ya fue realizado, una alternativa es utilizar **geom_col()** en lugar de **geom_bar()**.

```{r}
p + geom_col()
```

El gráfico se puede modificar en términos visuales.

```{r}
p <- ggplot(data = frecuencias,
            mapping = aes(x = sustan1,
                          y = porcentaje))

p + geom_col(fill = "gray55",
             color = "black") + 
    labs(x = "Consumo de alcohol",
         y = "Porcentaje (%)") + 
    scale_y_continuous(breaks = seq(0, 60, by = 10)) + 
    theme_bw()
```

### Gráfico de barras agrupado

Para analizar si la proporción de personas que consumen y no consumen alcohol difiere entre hombres y mujeres es necesario un **gráfico de barras agrupado**.

Se quiere calcular el porcentaje de consumo y no consumo de alcohol para hombres y mujeres de manera separada.

Al usar **group_by(sexo, sustan1)** se establece como primer nivel de agrupación el sexo, y posteriormente el consumo de alcohol.

```{r}
frecuencias <- datosSPSS %>% group_by(sexo, sustan1) %>% 
                             summarize(N = n()) %>% 
                             mutate(frecuencia_relativa = N / sum(N), 
                             porcentaje = round((frecuencia_relativa*100), 0))

frecuencias
```

El hecho de que los porcentajes de consumo y no consumo sumen 100% dentro de cada sexo indica que el cálculo se realizó correctamente.

Crear el gráfico de barras agrupadas requiere **mapear sustan1** a **fill**. Posteriormente, se necesita utilizar **geom_col()**, dado que los datos a visualizar han sido previamente calculados. Por último, se separan las barras para cada sexo utilizando **facet_grid(~ sexo)**.

```{r}
p <- ggplot(frecuencias, aes(x = sustan1, 
                             y = porcentaje, 
                             fill = sustan1))

p + geom_col(position = "dodge2") +
    facet_grid(~ sexo)
```

Con algunos ajustes en apariencia el gráfico se puede ver de la siguiente forma.

```{r}
p <- ggplot(frecuencias, aes(x = sustan1, 
                             y = porcentaje, 
                             fill = sustan1))

p + geom_col(position = "dodge2",
             color = "black") +
    labs(x = NULL, 
         y = "Porcentaje", 
         fill = "Sexo") +
    guides(fill = "none") +
    scale_y_continuous(breaks = seq(0, 70, by = 10)) +
    theme_bw() +
    facet_grid(~ sexo)
```

### Diagrama de barras apiladas

Otra manera de examinar si hay diferencias en la prevalencia de consumo de alcohol entre hombres y mujeres es con un **gráfico de barras apiladas**.

Para crear este gráfico se **mapea sexo** al **eje x** y **sustan1** a **fill**. Dado que se requiere el cálculo del conteo de observaciones, se utiliza **geom_bar()**.

```{r}
p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar()
```

Con algunos ajustes estético el gráfico es el siguiente.

```{r}
p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar() +
    theme_bw() +
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol")
```

Para comparar directamente las proporciones de cada grupo, se utiliza **position = "fill"** dentro de **geom_boxplot()**.

```{r}
p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar(position = "fill") +
    theme_bw() +
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol")
```

## Diagrama de cajas

### Diagrama de cajas simple

Los diagramas de cajas se pueden obtener con **geom_boxplot()**.

Se crea un diagrama de cajas para la **edad**. Por defecto, el gráfico es el siguiente.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(y = edad))

p + geom_boxplot()
```

Se puede ajustar el **eje x** para tener una interpretación más precisa del diagrama.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(y = edad))

p + geom_boxplot() +
    scale_y_continuous(breaks = seq(15, 30, by = 3))
```

Con más detalles (tema blanco y negro, y etiquetas de eje) se obtiene el siguiente gráfico.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(y = edad))

p + geom_boxplot(fill = "grey") +
    scale_y_continuous(breaks = seq(15, 30, by = 3)) +
    labs(y = "Edad de los participantes") +
    theme_bw()
```

### Diagrama de cajas agrupado

Se puede generar un diagrama de cajas agrupado mapeando una segunda variable al **eje x**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sexo,
                          y = edad))

p + geom_boxplot()
```

Una manera de diferenciar los grupos es mapear también la variable **sexo** a **fill**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sexo,
                          y = edad,
                          fill = sexo))

p + geom_boxplot()
```

La guía innecesaria se puede eliminar añadiendo **guides(fill = "none")**.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sexo,
                          y = edad,
                          fill = sexo))

p + geom_boxplot() +
    guides(fill = "none")
```

Con algunos detalles adicionales, el diagrama resultante es el siguiente.

```{r}
p <- ggplot(data = datosSPSS,
            mapping = aes(x = sexo,
                          y = edad,
                          fill = sexo))

p + geom_boxplot() +
    guides(fill = "none") +
    scale_y_continuous(breaks = seq(15, 30, by = 3)) +
    labs(x = "Sexo de los participantes",
         y = "Edad en años") +
    theme_bw()
```

## Gráfico de lineas 

Se graficarán las trayectorias de estrés psicológico de 5 sujetos ficticios en el dataset **datos_estres**.

```{r}
datos_estres <- read_sav("datos_estres.sav")

datos_estres
```

Se quiere examinar si, en promedio, ha ocurrido un cambio en el estrés psicológico. Para ello es necesario obtener el promedio de cada tiempo. Esto se puede realizar con resumenes agrupados.

```{r}
promedios <- datos_estres %>% group_by(tiempo) %>% 
                              summarize(M = mean(estres_total))

promedios
```

Se puede obtener un **gráfico de líneas** para observar estos promedios con **geom_line()**. El gráfico por defecto es el siguiente.

```{r}
p <- ggplot(data = promedios,
            mapping = aes(x = tiempo,
                          y = M))

p + geom_line()
```

Se realizan algunos cambios en la apariencia del gráfico. Agregar **geom_point()** permite asignar una marca para cada promedio, cuyo tamaño y forma se controla con los argumentos **size** y **shape**, respectivamente.

```{r}
p <- ggplot(data = promedios,
            mapping = aes(x = tiempo,
                          y = M))

p + geom_line(linetype = "dashed") +
    geom_point(size = 3, shape = 18) + 
    labs(x = "Tiempo",
         y = "Promedio de estrés psicológico") +
    theme_bw() +
    scale_x_continuous(labels = c("2015", "2016", "2017", "2018", "2019"))
```

Adicionalmente, puede ser necesario obtener una mirada de las trayectorias individuales que llevaron a los promedios observados. Para lograr esto se necesita volver a utilizar el dataset original **datos_estres**, mapeando **estres_total** al **eje y**. 

También es necesario **mapear ID** a **group** dentro de **geom_line**.

```{r}
p <- ggplot(data = datos_estres,
            mapping = aes(x = tiempo,
                          y = estres_total))

p + geom_line(mapping = aes(group = ID))
```

Para distinguir cada trayectoria individual, puede ser útil mapear **ID** a **color**. Sin embargo, esta modificación requiere antes transformar **ID** a **factor**.

```{r}
datos_estres$ID <- factor(datos_estres$ID)
```

Junto con algunos cambios estéticos, el gráfico es el siguiente.

```{r}
p <- ggplot(data = datos_estres,
            mapping = aes(x = tiempo,
                          y = estres_total,
                          color = ID))

p + geom_line(mapping = aes(group = ID), size = 0.7) + 
    labs(x = "Tiempo",
         y = "Puntajes de estrés psicológico",
         color = "N° de identificación") +
    theme_bw() +
    scale_x_continuous(labels = c("2015", "2016", "2017", "2018", "2019"))
```

## Gráfico de área

Otra geometría que ayuda a representar el cambio de una variable a través del tiempo es **geom_area()**. Por defecto, el gráfico para los promedios de estrés psicológico sería el siguiente.

```{r}
p <- ggplot(data = promedios,
            mapping = aes(x = tiempo,
                          y = M))

p + geom_area()
```

Se agregan ajustes adicionales.

```{r}
p <- ggplot(data = promedios,
            mapping = aes(x = tiempo,
                          y = M))

p + geom_area(alpha = 0.3) +
    labs(x = "Tiempo",
         y = "Promedio de estrés psicológico") +
    theme_bw() +
    scale_x_continuous(labels = c("2015", "2016", "2017", "2018", "2019"))
```

## Diagrama de dispersión

El diagrama de dispersión se crea mapeando dos variables numéricas a los **ejes x e y**, respectivamente, y aplicando **geom_point()** sobre el mapeo.

Para ilustrar la creación de este gráfico, se utiliza el dataset **msqR** del paquete **psychTools**. Específicamente, se analiza la relación entre la extraversión (**Extraversion**) y sociabilidad (**Sociability**).

```{r}

library(psychTools)

p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability))

p + geom_point()
```

Se agregan algunos detalles.

```{r}

p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability))

p + geom_point() + 
    theme_bw() + 
    scale_y_continuous(breaks = seq(0, 20, by = 2)) +
    labs(x = "Extraversión",
         y = "Sociabilidad")

```

### Mapeo de tercera variable discreta a color

Se mapea **gender (1 = Hombre, 2 = Mujer)** a color, para distinguir los datapoints que corresponden a cada sexo. 

Dado que la variable **gender** es discreta, es importante que esté codificada como **factor** o **vector de caracteres**. 

Antes de crear el gráfico se eliminan también los casos con datos perdidos en **gender**.

```{r}
msqR <- msqR %>% 
        mutate(gender = case_when(gender == 1 ~ "Hombre",
                                  gender == 2 ~ "Mujer"))

msqR <- msqR[complete.cases(msqR$gender), ]
```

El gráfico resultante es el siguiente.

```{r}
p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability,
                          color = gender))

p + geom_point()
```

El gráfico se puede mejorar agregando algunos detalles.

```{r}
p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability,
                          color = gender))

p + geom_point() +
    labs(x = "Extraversión",
         y = "Sociabilidad",
         color = "Sexo") +
    theme_bw() +
    scale_x_continuous(breaks = seq(0, 20, by = 3)) +
    scale_y_continuous(breaks = seq(0, 13, by = 2))
```

### Gráfico segmentado según tercera variable discreta

Otra manera de separar los datos según una variable discreta es utilizar **facetas**.

```{r}
p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability))

p + geom_point() +
    labs(x = "Extraversión",
         y = "Sociabilidad") +
    theme_bw() +
    scale_x_continuous(breaks = seq(0, 20, by = 3)) +
    scale_y_continuous(breaks = seq(0, 13, by = 2)) +
    facet_wrap(~ gender)
```

### Mapeo de tercera variable numérica a color

En lugar de una variable discreta, se puede mapear una variable numérica a **color**. En este caso, se utiliza **neuroticismo (Neuroticism)**.

```{r}
p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability,
                          color = Neuroticism))

p + geom_point() +
    labs(x = "Extraversión",
         y = "Sociabilidad",
         color = "Neuroticismo") +
    theme_bw() +
    scale_x_continuous(breaks = seq(0, 20, by = 3)) +
    scale_y_continuous(breaks = seq(0, 13, by = 2))
```

La escala de neuroticismo (variable numérica) se representa con una **gradiente** que va desde el azul claro al azul oscuro.

## Detalles adicionales

### Cambiar colores específicos de un gráfico

Para modificar colores específicos de un gráfico, se necesitan aplicar funciones **scale** sobre el mapeo que establece los colores, indicando **manual**. Los colores se controlan con el argumento **values** dentro de esta función.

En gráficos de barras, esto se puede realizar con los siguientes códigos.

```{r}

# Ejemplo 1 

p <- ggplot(data = datosSPSS,
            mapping = aes(x = sustan1,
                          fill = sustan1))

p + geom_bar() + 
    scale_fill_manual(values = c("lightblue", "tan1"))

# Ejemplo 2

p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar() +
    theme_bw() +
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol") + 
    scale_fill_manual(values = c("seagreen3", "thistle3"))
```

### Anotaciones

Se pueden hacer anotaciones directamente en un gráfico con **annotate()**. 

**annotate()** no es un geom, sino que utiliza los geoms especificados. Esto incluye los argumentos **x**, **y**, **size**, **color**, y **label**. Los argumentos **hjust** y **vjust** permiten que el texto esté justificado. El código **\n** agrega una nueva línea a la anotación.

Dentro de **annotate()**, el argumento **geom = "text"** permite crear anotaciones de texto.

```{r}

p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability))

p + geom_point() + 
    theme_bw() + 
    scale_y_continuous(breaks = seq(0, 20, by = 2)) +
    labs(x = "Extraversión",
         y = "Sociabilidad") +
    annotate(geom = "text",
             x = 10,
             y = 11,
             label = "La relación entre las variables \n es bastante positiva",
             vjust = 0) 

```

También se puede destacar un área rectangular del gráfico con **geom = "rect"**.

```{r}

p <- ggplot(data = msqR,
            mapping = aes(x = Extraversion,
                          y = Sociability))

p + geom_point() + 
    theme_bw() + 
    scale_y_continuous(breaks = seq(0, 20, by = 2)) +
    labs(x = "Extraversión",
         y = "Sociabilidad") +
    annotate(geom = "text",
             x = 10,
             y = 11,
             label = "La relación entre las variables \n es bastante positiva",
             vjust = 0) +
    annotate(geom = "rect",
             ymin = 10.8,
             ymax = 12,
             xmin = 7,
             xmax = 13,
             fill = "red4",
             alpha = 0.2)

```

### Fuente del gráfico

Se puede modificar la **fuente** de un gráfico usando la librería **showtext**.*

Primero se carga la fuente con **font_add()** y **showtext_auto()**.

Luego se utiliza el argumento **text** dentro de **theme()**. Este se define con la función **element_text()**, donde los argumentos **family** y **size** controlan el tipo y tamaño de fuente, respectivamente.

```{r}
library(showtext)

# Times new roman

font_add("Times New Roman", regular = "times.ttf")

showtext_auto()

p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar() +
    theme_bw() +
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol") + 
    theme(text = element_text(family = "Times New Roman", 
                              size = 23))

# Century Schoolbook

font_add("Century Schoolbook", regular = "censcbk.ttf")

showtext_auto()

p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar() +
    theme_bw() +
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol") + 
    theme(text = element_text(family = "Century Schoolbook", 
                              size = 23))

# Calibri

font_add("Calibri", regular = "calibri.ttf")

showtext_auto()

p <- ggplot(datosSPSS, aes(x = sexo,
                           fill = sustan1))

p + geom_bar() +
    theme_bw() +
    scale_y_continuous(breaks = seq(0, 600, by = 50)) + 
    labs(x = "Sexo",
         y = "N",
         fill = "Consumo de alcohol") + 
    theme(text = element_text(family = "Calibri", 
                              size = 23))

```

### Unir gráficos con patchwork

La librería **patchwork** permite unir fácilmente diferentes gráficos.

El operador **|** une gráficos en fila.

```{r}
library(patchwork)

p1 <- ggplot(data = datosSPSS,
             mapping = aes(x = felicidad)) + 
      geom_bar() + 
      theme(text = element_text(family = "Century Schoolbook", 
                                size = 23))

p2 <- ggplot(data = datosSPSS,
             mapping = aes(x = sustan1)) + 
      geom_bar() + 
      theme(text = element_text(family = "Century Schoolbook", 
                                size = 23))

p3 <- ggplot(data = datosSPSS,
             mapping = aes(x = sexo)) + 
      geom_bar() + 
      theme(text = element_text(family = "Century Schoolbook", 
                                size = 23))

p1 | p2 | p3
```

El operador **/** une gráficos de manera vertical.

```{r}
p1 / p2 / p3
```

Los operadores **|** y **/** se pueden combinar utilizando **()**.

```{r}
p1 / (p2 | p3)
```
