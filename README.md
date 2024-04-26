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
SELECT empleado.dni, empleado.nombre, empleado.apellido
FROM empleado
JOIN sector ON empleado.id_sector = sector.nombre
```

## **Segundo Ejercicio**
Una búsqueda que devuelva algunos registros (+ de 1) pero no todos

```sql
SELECT `DNI_D`, `ombre
FROM `Desarolladores`
ORDER BY `Nombre`;
```

```sql
SELECT `ID_estudio`, `nombre_estudio`
FROM `Estudio`
ORDER BY `nombre_estudio`;
```

```sql
SELECT `ID_Oficina`, `Oficina`
FROM `Oficina`
ORDER BY `Oficina`;
```

```sql
SELECT `ID_Tienda`, `Nombre`
FROM `Tiendas`
ORDER BY `Nombre`;
```

## **Tercer Ejercicio**
Una consulta que agregue un nuevo registro

```sql
INSERT INTO `Desarolladores` (`DNI_D`, `Nombre`) VALUES (`200631`, `Roberto`);
```

```sql
INSERT INTO `Estudio` (`ID_estudio`, `nombre_estudio`) VALUES (`28`, `Robertogaming`);
```

```sql
INSERT INTO `Oficina` (`ID_Oficina`, `Oficina`) VALUES (`69`, `RobertoOficina`);
```

```sql
INSERT INTO `Tienda` (`ID_Tienda`, `Nombre`) VALUES (`19`, `tiendaRoberto`);
```
