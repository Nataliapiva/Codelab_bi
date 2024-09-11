# Codelab_bi


<div align "center">
<h1 align="center"> Hola, soy Natalia Andrea Pinzón Vásquez 
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="35"> </h1>
<ing src="https://github.com/Danielakato/codelAB_bi/commit/bf2b7c96d2894da5f193319745e47c9c651201ea">  

---

<img src="https://media.giphy.com/media/ObNTw8Uzwy6KQ/giphy.gif" width="30px">&nbsp;***Datos curiosos sobre mí***
- 👩🏻‍💼Soy Estudiante de Administración de Empresas.
  
- 💻 Actualmente estoy aprendiendo lenguage de programación phyton y SQL, con el objetivo de poderlos aplicar en la toma de decisiones estratégicas de los negocios. 


## **Tabla de Contenidos**
- [Introducción código](#Introducción)
- [Instalación](#Instalación)
- [Primeros pasos: Creación base de datos](#Creación_base_de_datos)
- [Generar y Guardar Tabla de Clientes](#Generar-y-Guardar-Tabla-de-Clientes)
- [Generar y Guardar Datos de Sucursales](#Generar-y-Guardar-Datos-de-Sucursales)
- [Generar y Guardar Tabla de Transacciones](#Generar-y-Guardar-Tabla-de-Transacciones)
- [Generar y Guardar Tabla de Tipo de Transacciones](#Generar-y-Guardar-Tabla-de-Tipo-de-Transacciones)
- [Verificar la Creación de Tablas en SQLite3](#Verificar-la-Creación-de-Tablas)
- [Explicación de Gráficas](#Explicacion-de-graficas)
- [Cierre](#Cierre)
- [Autor(es)](#Autores)

 
# Introducción
A continuación, presento un ejercicio práctico de Business Intelligence, haciendo uso de una base de datos SQLite3 con el objetivo de almacenar información de transacciones financieras, registrando diversos datos de clientes, sucursales, e información de las transacciones. 

# Instalación
Para llevar este ejercicio práctico a cabo, iniciaremos con la instalación de la libería faker, con el código '!pip install faker'

Posterior a eso, se importaron las siguiente librerías con el código 'import':

1. SQLite3: Libería que permite trabajar con bases de datos en Python.

2. Pandas as pd: Herramienta poderosa para manejar y analizar datos en Python.

3. Requests: Esta librería se utiliza para hacer solicitudes a internet, como descargar datos de una página web.

4. Random y uuid: Utilizadas para generar datos aleatorios y únicos.

5. Faker: Con el comando 'from faker import Faker', se busca importar la libería Faker, que ya fue instalada anteriormente para la creación de datos falsos, que nos son de utilidad para el desarrollo del ejercicio.

6. numpy as np: Es utilizado para trabajar con matrices y datos numéricos en general.

7. shutil: Se utiliza para copiar y mover archivos.

8. missingno as msno: Se utiliza para visualizar y analizar datos faltantes.

Una vez realizadas todas las importaciones de las liberías y herramientas, se monta en Google Drive con el comando 'drive.mount('/content/drive'), de tal forma que el script pueda leer o guardar archivos directamente desde allí.

Continuamos con incluir la ruta al archivo db con la ruta a google drive, y luego conectar a la base de datos.

Lo anterior se ve así, 

![image](https://github.com/user-attachments/assets/ed7cf770-7852-41b9-9d58-44a95080a717)


# Creación base de datos

Para la creación de la base de datos, los primeros pasos a dar son: 

1. La instalación de Faker, permitiendo la generación de datos falsos.
2. La conexión a la base de datos, a través del comando 'conn=sqlite3.connet('financial_data.db') para la creación de la base de datos llamada 'financial_data.db'.
3. La función para ejecutar consultas SQL: 'def execute_query(query, conn):', gracias a este comando se asegura que la acción sea ejecutada correctamente y sea registrado cualquier cambio generado en el código.

Lo anterior se ve así, 
![image](https://github.com/user-attachments/assets/d153c91c-e888-4f48-854c-4139a28e9143)


# Generar y Guardar Tabla de Clientes
El código crea varias tablas dentro de la base de datos financial_data.db para almacenar diferentes tipos de información, entre estos está la información del cliente, relacionado a su nombre, dirección, número de teléfono y correo.

Para esto, se genera la función para obtener datos de clientes desde randomuser API, con el siguiente comando:
![image](https://github.com/user-attachments/assets/9fa526da-47f4-4769-93a3-f03f0d5dd81c)

Posterior a eso, se crea la tabla de clientes y se guarda en SQLite3 con la función:
![image](https://github.com/user-attachments/assets/23fc197e-8a6f-4e0b-b579-30388e2798c1)


# Generar y Guardar Tabla de Sucursales
Para la creación de datos falsos de las sucursales, se hace uso de faker.


![image](https://github.com/user-attachments/assets/9cdebe5a-f1a8-4961-9332-6df6fa9aa2c3)
***Espacio educativo para entender la diferencia entre Faker y la API***


FAKER: 
- Librería de Python que permite generar datos falsos localmente.
-  Puedes configurar y personalizar los datos generados, especificando formatos específicos o incluir detalles particulares.
-  Generación rápida de grandes cantidades de datos.
-  No requiere de internet.

API de randomuser.me
API pública que genera y proporciona datos falsos similares a los de Faker con la diferencia de:
- Los datos se generan en un servidor remoto, y tu script hace una solicitud HTTP para obtenerlos.
- randomuser.me tiene un conjunto predefinido de datos que puede devolver. Aunque puedes especificar ciertos parámetros (como la nacionalidad), estás limitado a lo que la API ofrece.
- Requiere de conexión de internet para el uso de la API.
- Limitaciones en la cantidad de datos que se pueden solicitar en un periodo de tiempo.
- No requiere de la instalación de una librería.

***Fin del espacio educativo***
![image](https://github.com/user-attachments/assets/fd80753b-792d-4da8-bd94-ec33b185abba)

De acuerdo con lo anterior, en este caso, se hace uso de faker para la creación de la tabla de sucursales, haciendo uso del siguiente comando:

![image](https://github.com/user-attachments/assets/e5fc41ed-1c62-4b13-8d6f-e2e1ff3e00dc)


# Generar y Guardar Tabla de Tipos de Transacciones
Siguiendo la misma función pero enfocada en la creación de datos de tipos de transacciones, se crea la tabla y se guarda en el SQLite3, como se ve a continuación:

![image](https://github.com/user-attachments/assets/6285bd09-fc8c-4b85-adfc-5fa6cbe032e4)


# Generar y Guardar Tabla de Transacciones
En este chunk se genera la tabla de transacciones y se guarda en SQLite3. En dicha tabla, se tiene en cuenta datos sobre transacciones fraudulentas, id de la transacción, id del cliente que realizó dicha transacción, fecha, cantidad, lugar donde se realizó la operación, y el tipo de transacción.

![image](https://github.com/user-attachments/assets/31328a30-9cc3-496b-a909-32ee75b9e9b9)

Así mismo, se introducen el número de transacciones fraudulentas con la función 'n_fraud=10', siendo el 10, el número de transacciones fraudulentas generadas. 
Posterior a eso, se asigna branch_id para aquellas transacciones en la tienda "in-store", mientras que para las transacciones online, branch_id se puede establecer en None.

Lo anterior se puede ver en el siguiente código:
![image](https://github.com/user-attachments/assets/e76f9bba-bd0d-41f6-b132-8e304140af76)

# Verificar la Creación de Tablas en SQLitte3

En este apartado o chunk, se busca verificar que las tablas generadas anteriormente en el código, se hayan generado y cerrado de manera correcta, a través del siguiente código:

![image](https://github.com/user-attachments/assets/55cbd61b-4078-43ca-a7cd-33879ccc9527)

Dentro de la verificación de la creación de tablas se enlista las tablas existentes e imprime los resultados, consultando SQL SELECT name FROM squlite_master WHERE type_'table' y ejecutándola con el código pd.read_sql() y almacenando todas las tablas con el código DataFrame (tables).

Por último, y recordando que al inicio del ejercicio fue creado un archivo desde Drive con el nombre de 'financial_data.db', se debe comandar el almacenamiento de nuestro trabajo en dicho archivo de Google Drive, para luego copiar el archivo de la base de datos a Google Drive.

Lo anterior, se puede observar a continuación:
![image](https://github.com/user-attachments/assets/a73126fe-6321-41c1-a7f0-29576332cb29)

# Explicación de Gráficas
A continuación se presentan las tablas generadas y demás estadísticas descriptivas que ofrecen información útil sobre la completitud de los datos, realizando un conteo en el primer gráfico de registros por columna en la tabla de transacciones y conteo de los valores no nulos en las segunda gráfica, gracias a la librería missingno. Ambos gráficos presentados a continuación presentan un comportamiento similar donde cada barra cuenta con la misma cantidad de registros, lo que nos permite verificar la completitud de los datos en cada transacción.

![image](https://github.com/user-attachments/assets/43adaf46-22a8-48d9-a126-291e467adaec)
![image](https://github.com/user-attachments/assets/2d318fba-45d5-4358-a003-676bcd59386b)

**Matriz de estadísticas descriptivas
![image](https://github.com/user-attachments/assets/8409916a-e0c8-4559-be3d-2733f99e992d)
A partir de esta matriz podemos identificar una mayor concentración de los datos transaccionales evidenciados con un color rojo, el cual indica su gran cantidad con respecto al conjunto de datos fraudulentos.

**Distribución de la variable de datos transaccionales
Por último presentamos el gráfico de distribución de datos de transaction_amount, donde podemos evidenciar un comportamiento interesante en la frecuencia de los datos entre el rango 0-100, mientras que los datos disminuyen a medida que los datos de transacción más bajos cuentan con una menor frecuencia.
![image](https://github.com/user-attachments/assets/e0c5ee7d-7818-4cfa-bde6-405eb975b330)


# Cierre
Espero este ejercicio haya sido de gran utilidad, al igual que todos los lectores, hayan podido comprender un poco más sobre el lenguaje de programación de Python y SQLite3.

<div align "center">
<h1 align="center"> ¡NOS VEMOS A LA PRÓXIMA!
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="35"> </h1>
<ing src="https://github.com/Danielakato/codelAB_bi/commit/bf2b7c96d2894da5f193319745e47c9c651201ea">  

  ![image](https://github.com/user-attachments/assets/cf5bf8f6-6d02-4d3d-9793-69661c527a9d)

# Autores
Natalia Andrea Pinzón Vásquez


