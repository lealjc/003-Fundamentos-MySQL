# 003-Fundamentos-MySQL
Básico / Introducción a Base de Datos / Fundamentos MySQL / Postwork


<hr>
<b>Estos son las instrucciones que utilice para el Postwork de la sesión 3.</b>

<hr>


1.	Haz que tu carpeta de trabajo sea Introduccion-a-Bases-de-Datos/Sesion-03/Postwork/

Si tengo al menos dos archivos csv.
<br>
<br>

2.	Copiar la carpeta Datos creada en Sesion-02/Postwork/ y moverse a la carpeta Datos/

Copie los datos:
cp -a ../../sesion-02/postwork/Datos .
<br>
<br>

3.	Para cada archivo CSV realizar el proceso:

•	Analizar contenido del archivo
-	Revise el contenido de los dos archivos

•	Definir lista de campos y tipos de datos para cada uno
-	head cat_ur.csv<br>
001, DELEGACION ESTATAL EN AGUASCALIENTES, AGUASCALIENTES, AGS<br>
002, DELEGACION ESTATAL EN BAJA CALIFORNIA, BAJA CALIFORNIA, BC<br>
003, DELEGACION ESTATAL EN BAJA CALIFORNIA SUR, BAJA CALIFORNIA SUR, BCS<br>
004, DELEGACION ESTATAL EN CAMPECHE, CAMPECHE, CAMP<br>
005, DELEGACION ESTATAL EN COAHUILA, COAHUILA, COAH<br>
006, DELEGACION ESTATAL EN COLIMA, COLIMA, COL<br>
007, DELEGACION ESTATAL EN CHIAPAS, CHIAPAS, CHIS<br>
008, DELEGACION ESTATAL EN CHIHUAHUA, CHIHUAHUA, CHIH<br>
010, DELEGACION ESTATAL EN DURANGO, DURANGO, DGO<br>
011, DELEGACION ESTATAL EN GUANAJUATO, GUANAJUATO, GTO<br>

-	id_ur carácter 3, nombrel carácter 80, nombrec carácter 20, abrv carácter 3


-	head estadis.csv<br>
2019, DIC, 021, 67, 0, 0<br>
2019, DIC, 021, 184, 0, 0<br>
2019, DIC, 002, 34, 0, 0<br>
2019, DIC, 002, 59, 0, 0<br>
2019, DIC, 002, 105, 0, 0<br>
2019, DIC, 002, 518, 0, 0<br>
2019, DIC, 002, 522, 0, 0<br>
2019, DIC, 006, 80, 0, 0<br>
2019, DIC, 006, 122, 0, 0<br>
2019, DIC, 006, 496, 0, 0<br>

-	año integer, mes carácter 3, id_ur carácter 3, id_ebdi integer, altas integer, bajas integer.



•	Realizar conexión al SErvidor MariaDB/MySQL usando el comando mycli
-	mycli -h  ec2-35-167-226-182.us-west-2.compute.amazonaws.com -u root -p bedu0 583 -P 3306 --local-infile true




•	Hacer uso de tu base de datos con la instrucción SQL USE
- CREATE jcleal_Postwork;
- USE jcleal_Postwork;


•	Crear la tabla usando la instrucción CREATE en SQL
-	CREATE TABLE cat_ur (id INTEGER, nombrel VARCHAR(80), nombrec VARCHAR(20), abrv VARCHAR(3))
-	CREATE TABLE estadis (ano INTEGER, mes VARCHAR(3), id_ur VARCHAR(3), id_ebdi INTEGER, altas INTEGER, bajas INTEGER);


•	Importar datos a la tabla usando la instrucción LOAD y habilitando los permisos para mycli con la opción --local-infile true
-	LOAD DATA LOCAL INFILE "cat_ur.csv" INTO TABLE cat_ur FIELDS TERMINATED BY ",";
-	LOAD DATA LOCAL INFILE "estadis.csv" INTO TABLE estadis FIELDS TERMINATED BY ",";



•	Validar que los datos se hayan importado correctamente haciendo uso de la instrucción SELECT tanto a nivel de campos, como en el número de registros importados
-	SELECT * FROM cat_ur;
-	SELECT * FROM estadis;

  		 



