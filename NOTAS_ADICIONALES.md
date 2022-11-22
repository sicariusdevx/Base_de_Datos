# Acceso al moodle

http://187.217.4.141/~edc/moodle/
Folio de usuario / curp*p

# Historia de las bases de datos

https://www.thinkautomation.com/histories/the-history-of-databases/

https://www.quickbase.com/articles/timeline-of-database-history

https://survey.stackoverflow.co/2022/

http://jovenes.itcomplements.com/

# DISEÑO LÓGICO DE BASE DE DATOS

## Modelo entidad - relación

Forma gráfica de representar la forma en que están estructuradas las bases de datos relacionales.
Se denomina ENTIDAD a la tabla y se representa con una figura rectangular.
Por medio de líneas se conecta a sus atributos (ovalos o círculos) que pueden ser:
-Atributos compuestos y simples (con atributos derivados o sin ellos)
-Atributos de un sólo valor o múltiples (doble círculo o línea) cuando puede tener varias asignaciones
-Atributo derivado (aquel que se puede derivar, generar o deducir a partir de otros atributos, se representa con un óvalo punteado)

Un atributo tiene diversas propiedades:
+Dominio: conjunto de valores que puede tomar
+Valor nulo que tienen aquellos que no cuentan con un valor concreto

Cardinalidad
Establece la relación entre diferentes entidades. Se simboliza con un rombo y se identifica normalmente con un verbo.
A ambos lados de la relación debe conectarse el numeral o variable que identifica la relación entre ambas entidades.


# Normalización 

Proceso de simplificación de los datos (atributos)
claves foráneas: aquellas que se importan desde otra entidad


# Gestores de base de datos

## Línea de comandos

La gestión de base de datos relacional (SQL) puede realizarse mediante línea de comandos

![image](https://user-images.githubusercontent.com/20374059/200018033-32665c2b-00af-42f7-a3a0-873f3a37773f.png)

![image](https://user-images.githubusercontent.com/20374059/200018197-cfb00953-5846-43a9-b52a-a29679feea61.png)

## MySQL

![image](https://user-images.githubusercontent.com/20374059/200018424-9b1896e2-3b30-4623-a9af-732c430659c3.png)

![image](https://user-images.githubusercontent.com/20374059/200018611-474887ad-0124-461a-aa3d-8182fbd358a9.png)

## phpMyAdmin

![image](https://user-images.githubusercontent.com/20374059/200018538-e32c3edd-2ee5-4e46-a22c-2d7efa3567db.png)

![image](https://user-images.githubusercontent.com/20374059/200019066-905153b3-28c7-4f1e-8a9c-d06a2c5b950e.png)

## db-fiddle (en línea)

Es una herramienta en línea para la elaboración de bases de datos. Recuerde que DDL y DML son normalmente realizados por dos figuras distintas: el operador de la base de datos y el analista de datos. En esta herramienta tendrá acceso a ambas funcionalidades por lo que es importante dedicar el espacio correcto al conjunto de comandos indicado.

[db-fiddle.com](https://www.db-fiddle.com)

![image](https://user-images.githubusercontent.com/20374059/200021627-7c8c73bc-23ab-4b43-973b-f53fa3ca7a94.png)

# Comandos

Se escriben en mayúsculas

## DDL

Tabla completa
https://www.db-fiddle.com/f/w27xWsmKA54ktiBYuP8CH1/2

EJERCICIO. Note que el último dígito especifica la versión de acuerdo a las veces que se ha guardado la base de datos
Correr continuamente la base de datos para verificar que no tiene errores.
Los comentarios en SQL van precedidos de un doble guión alto


CREATE DATABASE database_name;
Crea la base de datos.

USE database_name;
Establece la base de datos que utilizará en ese momento. En caso de no especificar el sistema puede hacer referencia a una base de datos distinta cargada de facto como parte de la interfaz.

```
CREATE TABLE database_name(
  atrib1 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  atrib2 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  atrib3 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  ...
  );
```
observe que el ultimo atributo NO DEBE DE LLEVAR COMA

Propiedades de los Atributos

```
PRIMARY KEY   Es una clave principal de las tuplas
NOT NULL      No se puede quedar vacío
```
Insertar datos:
```
INSERT INTO [tabla] VALUES ([dato_campo1],[dato_campo2],[dato_campo3]);
```

Datos nulos son aquellos que tienen un espacio ocupado en memoria o almacenamiento pero no tienen un valor asignado.

Datos vacíos carecen por completo de contenido y no ocupan espacio en memoria o almacenamiento.

Comentarios del código

-- comentario
/* sección comentada */

## DML

Los comandos de entrada de datos y de creación de tabla suelen ir entremezclados en el código ya que este es consecuencia de la sucesión de acontecimientos o sucesos que van conformando las tablas y toda la base de datos.

**Consultas en la tabla**

```
USE [nombre_database];

SELECT [nombre_campo1],[nombre_campo2],...   -- se puede utilizar un selector universal *
  FROM [nombre_tabla]
  WHERE [nombre_campo comparador condición];
```

Para establecer filtros más complejos se pueden utilizar los operadores lógicos AND, OR, XOR, NOT entre las diferentes comparaciones.

**Enlazar tablas**

Para poder hacer una consulta de dos tablas que comparten las claves foráneas se utiliza INNER JOIN.

```
SELECT [nombre_campo1_tabla1],[nombre_campo2_tabla2],...  
  FROM [nombre_tabla1] INNER JOIN [nombre_tabla2] ON [nombre_tabla2.nombre_campo2_tabla2] = [nombre_tabla1.nombre_campo1_tabla1]
  WHERE [nombre_campo comparador condición];
```

En caso de que ambas tablas se encuentren relacionadas pero existan datos que no se encuentran enlazados en ambas tablas se utiliza LEFT JOIN. El resultado será que nos mostrará todos los campos de la primera tabla solicitados con las condiciones especificadas aunque tengan campos nulos o no se encuentren reflejados en la tabla 2.

```
SELECT [campo1_tabla1],[campo2_tabla2],...  
  FROM [tabla1] LEFT JOIN [tabla2] ON [tabla2.campo2_tabla2] = [tabla1.campo1_tabla1]
  WHERE [nombre_campo comparador condición];
```

| Paulo   |	45   |	2021-04-13 |
| Ángeles |	null |	null       |

Las búsquedas siguen los vínculos establecidos en el modelo entidad-relación. Por ello si queremos mostrar los datos relacionados entre dos tablas que se encuentran relacionadas mediante otras entidades debemos declarar todas las relaciones.

```
SELECT [nombre_campo1_tabla1],[nombre_campo3_tabla3],...
  FROM [tabla1] INNER JOIN [tabla2] ON [tabla2.claveforanea_tabla2] = [tabla1.claveforanea_tabla1]
  INNER JOIN [tabla3] ON [tabla3.claveforanea_tabla3] = [tabla2.claveforanea_tabla2];
```


Actualizar y modificar datos de la tabla (sin acceso a DDL)
```
UPDATE [tabla1]
  SET [campo1_tabla1] = 'nuevo_dato';
  WHERE [campo2_tabla1] = [condición];
```


https://programacionymas.com/blog/como-funciona-inner-left-right-full-join

Las bases de datos se pueden bifurcar o escindir (*fork*)  lo que permite establecer versiones de la misma.

biblioteca v2

https://www.db-fiddle.com/f/jaDc3k5ZuK1AnA9GX2SoDr/0

https://www.db-fiddle.com/f/jaDc3k5ZuK1AnA9GX2SoDr/1

tienda v1

https://www.db-fiddle.com/f/xmWgvuRDyMs8K2t1auepFV/1

## Operaciones dentro de la base de datos

https://www.db-fiddle.com/f/b3Fuj6Py7MS5aYfAxbPqp3/0

## Triggers

https://www.db-fiddle.com/f/jSuMQ8XbVW4xfgD2NnXeVo/0

## Subconsultas

https://www.db-fiddle.com/f/muGXYTBaMtZNA9c6xRQjf/0

INNER JOIN, LEFT JOIN y RIGHT JOIN permite hacer uniones de los datos de tablas, sin embargo, no permite hacer subconsultas limitadas a los datos de tabla2

Para eso utilizamos el método de subconsulta. Ventaja: la búsqueda puede ser más específica. Desventaja: es un método de consulta más lento e ineficaz en tablas de datos grandes.

```
SELECT [campos_tabla1]
   FROM [tabla1] 
   WHERE [campo_foraneo_tabla1] IN 
   (SELECT [campo_privado_tabla2] 
      FROM [tabla2] 
      WHERE [campo_buscado] = [data]);
```

## Evaluaciones

### Evaluación 6 Creación de una base de datos

https://www.db-fiddle.com/f/p7Zb8opeFYoHkqxMfn39xN/0

### Evaluación 7 Funciones en SQL

https://www.db-fiddle.com/f/p7Zb8opeFYoHkqxMfn39xN/3

### Evaluación 8 Disparadores

https://www.db-fiddle.com/f/j8TPAT8yACMYacSQfaeXck/0
https://www.db-fiddle.com/f/j8TPAT8yACMYacSQfaeXck/2

### Evaluación 9 Operaciones en Base de datos

https://www.db-fiddle.com/f/p7Zb8opeFYoHkqxMfn39xN/4

### proyecto final

https://www.db-fiddle.com/f/cMjAjtRUAJELAoJysypidh/0
https://www.db-fiddle.com/f/cMjAjtRUAJELAoJysypidh/1
https://www.db-fiddle.com/f/cMjAjtRUAJELAoJysypidh/2

# Páginas útiles

https://learnsql.com/blog/difference-between-where-and-having-clauses-in-sql/




