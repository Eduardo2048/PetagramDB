# Por favor descargue el archivo .zip y descomprímalo.  
# podra abrirlo y compilarlo con Android Studio.

## Petagram con persistencia.

Se ha dividido el proyecto a fin de que esté organizado bajo el modelo Vista-Presentador
La base de datos es una única tabla con los mismos componentes que el pojo.
public class Mascota {
    	private int i_ID;
private int i_Imagen;
private String s_Name;
private int i_Likes;	
. . . . 
}

La base de datos se denomina 	*DB_Mascotas*

Contiene una única tabla  :   *Mascotas* 

Con los siguientes componentes        
 
![image](https://github.com/user-attachments/assets/02162866-be0f-4edd-965b-258df964fded)






La tabla se crea con la siguiente sentencia SQL   ( En el código se han usado nombres desde la clase ConstantesDB ) 

*CREATE  TABLE MASCOTAS  ( Id  INTEGER PRIMARY KEY AUTOINCREMENT,  Imagen  INTEGER , Name  TEXT,  Likes  INTEGER )*

La tabla se puebla con 8 mascotas solamente si no tiene registros, para evitar cargar nuevas mascota en cada ejecución.

Cuando se presiona el hueso para dar un Like, se realiza un UPDATE de la DB incrementando el campo Like para ese registro en particular.

Para realizar la selección de las 5 mascotas con mayor número de likes  ( Boton con la imagen de una huella en la barra de tareas )

se utiliza la siguiente sentencia SQL

SELECT * FROM MASCOTAS ORDER BY Likes DESC

Al cargar los registros al recycle view se limita a 5 mascotas.
