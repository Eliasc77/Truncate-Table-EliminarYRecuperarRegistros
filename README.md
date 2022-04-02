# Truncate Table Eliminar Y RecuperarRegistros
#### La sentencia Truncate table vacia completamente la tabla y elimina todos y cada uno de los registros existentes y conserva intacta la estructura de dicha tabla a diferencia de cuando usamos delete.
cuando usamos **delete** oracle guarda una copia de los registros que son borrados y luego estos pueden ser recuperados.
> Ojo que cuando usamos truncate ya no es posible la recuperacion de dichos datos por que se libera todo el espacio en disco usado por la tabla, por lo tanto truncate es mucho mas rapido que delete.

 ```sql
select * from articulos;
```
 
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   |
 | ------------------|:----------------:|---------------:|-----------:|
 | 1            | impresora           |  Epson Stylus C45   |   1500   |
 | 2            | impresora           |  Epson Stylus C85   |   1500   |
 | 3            | impresora           |  Samsung 14   |   1500   |
 | 4            | teclado           |  ingles Biswal   |   1500   |
 | 8            | impresora           |  Dell   |   1500   |
 
___

  ```sql
delete from articulos;
```
 ```sql
select * from articulos;
```
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   |
 | ------------------|:----------------:|---------------:|-----------:|
 
 ___
 
 > Cuando usamos delete podemos recuperar los datos utilizando rollback;

```sql
rollback;
```
```sql
select * from articulos;
```
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   |
 | ------------------|:----------------:|---------------:|-----------:|
 | 1            | impresora           |  Epson Stylus C45   |   1500   |
 | 2            | impresora           |  Epson Stylus C85   |   1500   |
 | 3            | impresora           |  Samsung 14   |   1500   |
 | 4            | teclado           |  ingles Biswal   |   1500   |
 | 8            | impresora           |  Dell   |   1500   |
 
 ___
 
 > Ahora utilizaremos truncate
 
 ```sql
 truncate table articulos;
 ```
 ```sql
select * from articulos;
```
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   |
 | ------------------|:----------------:|---------------:|-----------:|
 
 ```sql
rollback;
```
 ```sql
select * from articulos;
```
 | CODIGO            | NOMBRE           |  DESCRIPCION   |   PRECIO   |
 | ------------------|:----------------:|---------------:|-----------:|
 ##### El sistema no podra recuperar los datos con el rollback, ya que truncate table elimina y desaparece por completo tanto de la base de datos como el disco de almacenamiento

 
 
 
