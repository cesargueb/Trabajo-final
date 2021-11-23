## Importar base de datos

Utilicen el siguiente comando para que puedan importar la base de datos. De esta manera, nos omitiremos enviar constantemente archivos cada vez que los modificamos. 

```
library( rio )
lkCSV = " https://raw.githubusercontent.com/cesargueb/TrabajoGrupal/main/subdata.csv "
subdata = importar ( lkCSV )
subdata = subdata [ ! subdata $ IngTotalPrin == 999999.0000 ,]
subdata = subdata [ ! subdata $ IngLiquiPrin == 999999.0000 ,]
subdata = subdata [ ! subdata $ IngLiquiSecun == 999999.0000 ,]
```
