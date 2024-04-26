# TP2 consulta de Bases de Datos  NO SE COPIEN VAGOS

### **Alumnos:** Juan Baader

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

```

## **Cuarto Ejercicio**
Hay que agrandar el equipo de caracterización, para eso Ravenna pidió agregar a una persona a su sector.

```sql
INSERT INTO empleado (dni, nombre, apellido, email, id_sector) VALUES (50456028, los, simuladores, aguantelosimuladores@hotmail.com, 4)
INSERT INTO telefono (numero, id_duenio) VALUES (54988338, 50456028);
```
INSERT INTO empleado (nombre, apellido, email, dni, id_sector)
VALUES (Daniel, Lopez, danilopez@gmail.com, 50456028, 4);
SET @dni = 50456028;
INSERT INTO telefono (telefono, id_duenio)
VALUES (48785838, @dni);


