# salaryinfo
Salary Info Application
------- OPEN PSQL ------------

CREATE USER salary WITH PASSWORD 'root';
ALTER USER salary CREATEDB;
ALTER USER salary WITH SUPERUSER;
\du
CREATE DATABASE infsalary OWNER salary;
GRANT ALL PRIVILEGES ON DATABASE infsalary to salary;
\c infsalary

-------- ABRIR CMD  ----------

python -m venv salinf
cd salinf
cd Scripts
activate
cd ..
###############Descargar repositorio, descomprimir carpeta y agregarla al entorno virtual
pip install --upgrade pip
pip install django
pip install psycopg2-binary
python -m pip install Pillow
pip install requests
cd salinf
python manage.py createsuperuser
>salary
>salary@postgres.com
password>root
password>root
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
