## Importar base de datos

```
library( rio )
lkCSV = " https://raw.githubusercontent.com/cesargueb/TrabajoGrupal/main/subdata.csv "
subdata = importar ( lkCSV )
subdata = subdata [ ! subdata $ IngTotalPrin == 999999.0000 ,]
subdata = subdata [ ! subdata $ IngLiquiPrin == 999999.0000 ,]
subdata = subdata [ ! subdata $ IngLiquiSecun == 999999.0000 ,]
```
