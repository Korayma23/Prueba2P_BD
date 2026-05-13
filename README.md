# Prueba2P_BD
1. Explicar Atomicidad
La atomicidad es una propiedad de las transacciones en bases de datos que indica que una operación debe ejecutarse completamente o no ejecutarse.
Si ocurre un error durante una transacción, Oracle realiza un ROLLBACK para evitar datos incompletos o inconsistentes.
Ejemplo:
Si se registra un boleto y luego su equipaje, ambas operaciones deben guardarse juntas. Si falla el registro del equipaje, también debe cancelarse el registro del boleto.

2. Explicar DELETE sin WHERE
Un DELETE sin cláusula WHERE elimina todos los registros de una tabla.
Ejemplo:
DELETE FROM PASAJERO;
Ese comando eliminaría todos los pasajeros registrados en la base de datos.
En este modelo, debido al uso de ON DELETE CASCADE, también podrían eliminarse automáticamente los boletos y equipajes relacionados.
Por eso es importante utilizar siempre la cláusula WHERE para controlar qué registros se eliminan.

3. Explicar ON DELETE CASCADE
ON DELETE CASCADE es una regla de integridad referencial aplicada a las claves foráneas.
Permite que, al eliminar un registro padre, Oracle elimine automáticamente todos los registros hijos relacionados.
En este modelo:
si se elimina un PASAJERO
también se eliminan automáticamente sus BOLETOS
y los EQUIPAJES relacionados a esos boletos
Esto evita registros huérfanos y mantiene la integridad de la base de datos.
