# Sem1_Proy1_BD

## Integrantes Grupo :
```
200310165 - José Abraham Navarro de León.
201503393 - José Daniel De León Ruiz.
201503893 - Brandon Javier Soto Castañeda.
```
## Pasos para crear la Base de Datos:

**1. Crear una carpeta para el repositorio Docker:**
```
	$ mkdir nombre_del_repositorio
```

**2. Ingresar a la carperta del repositorio:**
```
        $ cd nombre_del_repositorio
```

**3. Copiar archivos del repositorio de gitHub (scripts, Dockerfile, Readme.md, startDatabase):**
```
        $ git clone url_del_repo_en_gitHub
```

**4. Crear la imagen de la base de datos estando dentro de la carpeta del Dockerfile:**
```
        $ docker build -t my_mysql .
```

**5. Iniciar la base de datos con contenido de archivo .bash del repositorio:**
```
	-------------------------------------------------------------------------------------------------------------------------
	$ docker run --name some-mysql \
	  -e MYSQL_ROOT_PASSWORD=123456789 \
	  -d my-mysql \
	  --character-set-server=utf8mb4 \
	  --collation-server=utf8mb4_unicode_ci \
 	  --default-authentication-plugin=mysql_native_password
	-------------------------------------------------------------------------------------------------------------------------
```

**6. Correr la imagen de la Base de Datos:**
```
	$ docker exec -it some-mysql bash
```

**7. Ingresar a la Base de Datos e ingresar con password:**
```
	$ mysql -u root -p
```

**8. Ver el contenido de la imagen de Base de Datos:**
```
	$ show databases; 
```

**9. Usar una Base de Datos de la lista:**
```
	$ use nombre_de_la_BD
```

**10. Ver tablas de la Base de Datos seleccionada**
```
	$ show tables;
```

**11. Salir de la Base de Datos:**
```
	$ exit
```

**12. Salir de la imagen de Base de Datos a la instancia de AWS:**
```
	$ exit
```

## Subir imagen del repositorio local a Docker.com con los siguientes comandos:

**1. Posicionados en la carpeta del repositorio local:**
```
	$ docker tag nombre_del_repo_local nombre_del_repo_en_linea
	$ docker push nombre_del_repo_en_linea
```
## Posibles Errores :

### er_not_supported_auth_mode:
Si se encuentra con este error, haga los siguientes pasos:

**1. Entre al sistema del docker de la base de datos:**
```
	$ docker exec -it [id container] bash
```

**2.Ingrese al modo mysql y haga login con el usuario root:**
```
	$ mysql -u root -p
```

**3. Ingrese el siguiente comando para crear un usuario válido:**
```
	$ CREATE USER 'nuevo_nombre'@'%' IDENTIFIED WITH mysql_native_password BY 'nueva_contra';
```

**4. Ingrese el siguiente comando para darle permisos al nuevo usuario:**
```
	$ GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```
