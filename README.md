VERSION PYTHON Python 3.7.5 

********************CREACION BASE DE DATOS**************
CREACION DE BASE DE DATOS EN POSTGRES
0) Abrir la consola de postgres (PSQL)
1) Crear usuario y contrasena
	CREATE USER salary WITH PASSWORD 'root';	
	ALTER USER salary CREATEDB;
	ALTER USER salary WITH SUPERUSER;
	\du
	CREATE DATABASE infsalary OWNER salary;
	
	GRANT ALL PRIVILEGES ON DATABASE infsalary to salary;
	\c infsalary

*****************CREAR ENTORNO VIRTUAL************************
	python -m venv salinf_virtual

******************DESCARGAR REPOSITORIO***********************

	DESCARGAR REPOSITORIO DEL PROYECTO
		0) Descomprimir el archivo adjunto
		1) Pegar carpeta 'salinf' en la ruta base del entorno virtual

************CORRIENDO EL ENTORNO VIRTUAL*********************
	Abrir CMD
		#-- Ubiquese en la ruta del entorno virtual creado
		-> cd salinf_virtual
		-> cd Scripts
		-> activate

		***** INSTALAR DEPENDENCIAS *****
		pip install --upgrade pip
		pip install django
		pip install psycopg2-binary
		python -m pip install Pillow
		pip install requests
		
		#-- Ubicarse dentro del proyecto
		-> cd ..
		-> cd salinf	#Esta es la carpeta que fue descomprimida
		#-- Crear superusuario para administracion django
			-> python manage.py createsuperuser
			-> user : salary
			-> email:salary@postgres.com
			-> password : root
			-> password : root
		#Ejecutar servidor
			python manage.py runserver




---------- ABRIR PAGINA DE ADMINISTRACION ----------
> Ver que las tablas están vacias

---------- CARGAR LA BASE DE DATOS -----------------
> Abrir /reports/populate.py en modo edicion
> Ejecutar para cargar la base de datos
> Ver nuevamente los modelos

---------- PROBAR LOS ENDPOINTS -------------------------
GET  /reports/employees/ 					::: Muestra una lista de todos los usuarios creados
GET  /reports/employees/id/<int:employee_id> 			::: Muestra informacion de usuario por ID
GET  /reports/employees/name/<int:employee_name> 		::: Muestra informacion de usuario por Nombre
POST /reports/employees/create					::: Crea un nuevo usuario
POST /reports/gender/create					::: Crea un nuevo genero
POST /reports/discount/create					::: Crea un nuevo tipo de descuento
POST /reports/reporter/create					::: Crea un nuevo administrador de recursos humanos
GET  /reports/discounts						::: Muestra los tipos de descuentos existentes
GET  /reports/reporters						::: Muestra lista de administradores de recuersos humanos
POST /reports/monthly/create					::: Envia reporte de mes y año de un empleado
GET  /reports/fisco/<str:employee_name>/<int:year>/<int:month>	::: Extrae perfil fiscal de empleado en año y mes indicado


---------- EJECUTAR PRUEBAS ------------------------------
NO UTILICE POR FAVOR EL ARCHIVO tests.py EN SU DEFECTO UTILICE *populate.py* como se indica
anteriormente para poblar la base de datos
