# TP2 consulta de Bases de Datos  NO SE COPIEN VAGOS

### **Alumnos:** Juan Baader, Lucio Castielo y Manuel Coluccio

### **Año:** 2024

### **Curso:** 4B TIC

### **Profesor/a** Ignacio Vigilante

[Link a Github](https://github.com/juanpanpanyz/TP2-BasedeDatos)


<br>

## **Primer Ejercicio**
Santos quiere tener una lista completa de sus empleados, entonces necesita una consulta que devuelva el dni, nombre y apellido de todos los empleados junto con el nombre del sector en el que trabajan (no quiere la información de los empleados que no tienen un sector).
```sql
SELECT empleado.dni, empleado.nombre, empleado.apellido, sector.nombre
FROM empleado
JOIN sector ON empleado.id_sector = sector.id
```

## **Segundo Ejercicio**
Lampone necesita saber cuáles son las 3 salas más grandes de la empresa para llamar a una empresa de limpieza y pedirle cotización (necesita el id y la superficie de las 3 salas)(recordar que no deben utilizar TOP).
```sql
SELECT sala.superficie, sala.id
FROM sala
ORDER BY sala.superficie DESC
LIMIT 3;
```

## **Tercer Ejercicio**
Medina tiene que poder llamar a los empleados de su sector (Investigación), para eso pidió una lista de sus nombres, apellidos y números de teléfono. Si alguno tiene más de un teléfono Medina pidió tener todos.

```sql
SELECT empleado.nombre, empleado.apellido, telefono.numero AS numero
FROM empleado 
JOIN telefono ON telefono.dni_duenio = empleado.dni
WHERE empleado.id_sector = 1;
```

## **Cuarto Ejercicio**
Hay que agrandar el equipo de caracterización, para eso Ravenna pidió agregar a una persona a su sector.

```sql
INSERT INTO empleado (dni, nombre, apellido, email, id_sector) VALUES ("50456028", "los", "simuladores", "aguantelosimuladores@hotmail.com", 4);
```


## **Quinto Ejercicio**
Ahora Lampone quiere saber la información completa de las salas que tiene cada sector, incluyendo el nombre del sector al que pertenece y el apellido de su jefe. Además, si existe alguna sala sin un sector específico, requiere su información igualmente.

```sql
SELECT sala.*, sector.nombre, sector.nombre_jefe
From sala
LEFT JOIN sector ON sala.id_sector = sector.id;
```

## **Sexto Ejercicio**
Una política nueva de la empresa dice que los jefes de cada sector deben tener un mail de la empresa que sea su inicial, luego su apellido y finaliza con "@simuladores.com.ar". (Para este punto se necesitarán 4 queries separadas y no es necesario automatizarlas). 

```sql
UPDATE sector SET email_jefe = "GMedina@simuladores.com.ar" WHERE sector.id = 1;
UPDATE sector SET email_jefe = "PLampone@simuladores.com.ar" WHERE sector.id = 2;
UPDATE sector SET email_jefe = "MSantos@simuladores.com.ar" WHERE sector.id = 3;
UPDATE sector SET email_jefe = "ERavenna@simuladores.com.ar" WHERE sector.id = 4;
```

## **Septimo Ejercicio**
José Feller se va a jubilar, por lo que hay que sacarlo de la base de datos. (Ser lo más específico posible a la hora de borrarlo). 

```sql
DELETE FROM empleado WHERE empleado.dni = 8578124;
DELETE FROM telefono WHERE telefono.dni_duenio = 8578124;
```

## **Octavo Ejercicio**
Como queda un cupo vacante en el sector de planificación, Matías Miguens lo va a ocupar.

```sql
UPDATE empleado SET id_sector = 3 
WHERE dni = 43182902;
```

## **Noveno Ejercicio**
Se descubrió que Fernando Laguzzi estaba envuelto en actividades ilícitas, entonces Santos pidió que se le brindara toda su información, incluido el sector en el que trabaja, el apellido y el número de teléfono de su jefe.

```sql
SELECT empleado.dni, empleado.nombre, empleado.apellido, empleado.email, telefono.numero, sector.nombre, sector.apellido_jefe 
FROM empleado 
JOIN sector ON empleado.id_sector = sector.id 
JOIN telefono ON empleado.dni = telefono.dni_duenio WHERE empleado.dni = 18354680;
```

## **Diezavo Ejercicio**
Fernando Laguzzi se desvincula de la empresa, porque va a ir a la cárcel. Además, deben contratar un nuevo empleado para cubrir su puesto en el mismo sector. Este empleado deberá tener un número de teléfono asignado. (Para este punto se necesitan 3 queries).

```sql
DELETE FROM empleado WHERE empleado.dni = 18354680;
DELETE FROM telefono WHERE telefono.dni_duenio = 18354680;
```

```sql
INSERT INTO empleado VALUES(2, "Lucio", "Crack", "aguantechacrita@chaca.com", 2);
```

```sql
INSERT INTO telefono VALUES(1115347965, 2);
```

## **Bonus 1**
Santos quiere permitir que los empleados tengan más de un mail de contacto. Modificar la base de datos para que esto sea posible y luego explicar en qué se basa esta modificación (no es necesario utilizar consultas para modificar la estructura).

```sql

```

## **Bonus 2**
Realizar una consulta en SQL que devuelva la superficie total del edificio de la empresa. Para este punto deberán investigar las sentencias SQL en internet y encontrar alguna que permita realizar esta tarea.

```sql
SELECT SUM(superficie) AS superficie_total
FROM sala;
```

