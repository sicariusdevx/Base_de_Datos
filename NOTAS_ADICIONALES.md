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

https://www.db-fiddle.com/f/w27xWsmKA54ktiBYuP8CH1/0 
https://www.db-fiddle.com/f/w27xWsmKA54ktiBYuP8CH1/1
EJERCICIO. Note que el último dígito especifica la versión de acuerdo a las veces que se ha guardado la base de datos
Correr continuamente la base de datos para verificar que no tiene errores.
Los comentarios en SQL van precedidos de un doble guión alto


CREATE DATABASE database_name;
Crea la base de datos.

USE database_name;
Establece la base de datos que utilizará en ese momento. En caso de no especificar el sistema puede hacer referencia a una base de datos distinta cargada de facto como parte de la interfaz.

CREATE TABLE database_name(
  atrib1 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  atrib2 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  atrib3 TIPO_DATO(arg) ATRIBUTE_PROPERTY,
  ...
  );
observe que el ultimo atributo NO DEBE DE LLEVAR COMA

Propiedades de los Atributos
PRIMARY KEY   Es una clave principal de las tuplas
NOT NULL      No se puede quedar vacío





