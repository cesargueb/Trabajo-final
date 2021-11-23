# Importar base de datos

Para evitar, constantemente, enviarnos base de datos modificadas, les propongo que sigamos los siguientes pasos para tratar que todo esté automatizado.

## Base principal

Primero, es importante que cada quien tenga descargada la base de datos principal. En caso no la posean, pueden ingresar a este enlace de Drive para descargarla (no lo comparto por aquí por su peso). Aquí el enlace: https://drive.google.com/file/d/1V3-pH4BRPH6vgmv8L_hjvyxO1MALyAoW/view?usp=sharing

Luego, deben colocar los siguientes comandos para que puedan abrir la base en su environment. No olviden que deben abrir en R la carpeta en la que descargaron la data.

```
library(rio)
data=import("Base_Enaho.csv")
```

## Subdata

Luego, utilicemos el siguiente comando para poder importar la base de datos creada a partir de las variables seleccionadas (subdata). De esta manera, nos omitiremos enviar constantemente archivos cada vez que los modifiquemos. 

```
lkCSV = "https://raw.githubusercontent.com/cesargueb/Trabajo-final/main/subdata.csv"
subdata = import(lkCSV)
```
Cada vez que se elimine o agregue una variable, me encargaré de modificar la subdata aquí. De esta manera, ustedes solo necesitarían volver a correr los comandos anteriores. 

# Variables

Aquí les describo las variables que incluimos en la subdata (como les precisé, de existir alguna modificación, la agregaré), según la literatura que citaremos. 

## Variables de FACTORES PERSONALES

1. Sexo (1)Hombre y (2)Mujer: P207 (sexo)
2. Educación (¿Cuál es el último año o grado de estudios y nivel que aprobó ?): P301A (educ)
3. Edad en años cumplidos: P208A (edad)
4. Estado civil (¿Cuál es su estado civil o conyugal?): P209 (est_civil)

> Según la literatura, faltarían dos variables (Tipo de carrera y Raza), pero estas no son consideradas en la data; por ello, no se tomarán en cuenta.

## Variables de FACTORES LABORALES

5. Profesión laboral: P505 (profes) [Según el CIOU-88: https://docs.google.com/spreadsheets/d/1WQph7VqVjIdnYsBH5KcZKE2ZkJtzyIyx/edit?usp=sharing&ouid=107802791889917808463&rtpof=true&sd=true]
6. Total de horas trabajadas: P513T (horas)

> Según la literatura, faltarían tres variables (Viaje por trabajo, Teletrabajo y Rendimiento); sin embargo, la primera no está en el diccionario y las otras no son variables independientes. 

## Otras variables

7. Ingreso total (principal): P524A1 (IngTotalPrin)
8. Ingreso líquido (principal): P524E1 (IngLiquiPrin)
9. Ingreso total (secundario): P538A1 (IngTotalSecu)
10. ingreso líquido (secundario): P538E1 (IngLiquiSecun)

# ¿Categorización?

Directamente, en la subdata podrán observar que se han eliminado los valores perdidos (por ello, nos quedamos con 298 filas) y que ya se cambió el nombre a cada variable. Asimismo, podrán observar que todas están categorizadas como *variables numéricas,* esto lo determino así para que no haya problema al clausterizar. Una vez que determinemos, finalmente, las variables que utilizaremos, les compartiré por aquí los caomandos necesarios con los que hemos llegado a la subdata. 
