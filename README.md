# Truncate Table Eliminar Y RecuperarRegistros
#### La sentencia Truncate table vacia completamente la tabla y elimina todos y cada uno de los registros existentes y conserva intacta la estructura de dicha tabla a diferencia de cuando usamos delete.
#### cuando usamos delete oracle guarda una copia de los registros que son borrados y luego estos pueden ser recuperados.
> Ojo que cuando usamos truncate ya no es posible la recuperacion de dichos datos por que se libera todo el espacio en disco usado por la tabla, por lo tanto truncate es mucho mas rapido que delete.
