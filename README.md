# Pep_2_Dag_2024_2s
Instalación de Farmacias Populares en Maipú
Pep_2_Dag_2024_2s
Proyecto: Determinación de Ubicación Óptima para Farmacias Populares en Maipú
Este proyecto busca identificar los lugares óptimos para la instalación de farmacias populares en la comuna de Maipú utilizando un modelo espacial basado en PostgreSQL/PostGIS. Los criterios principales para determinar las ubicaciones incluyen la distancia mínima a predios de bajo nivel socioeconómico y la densidad poblacional de dichos predios.

Requerimientos del script Python 🐍
Configuración Inicial
Conexión a una base de datos PostgreSQL/PostGIS existente.
Procesamiento de la Información
El script debe ser capaz de:

Crear esquemas en la base de datos donde almacenará los datos de entrada y los resultados.
Poblar los datos de entrada en la base de datos:
Predios de la comuna de Maipú (capa espacial).
Manejar normativa asociada a los predios (atributos como zonificación, usos permitidos, restricciones, etc.).
Incorporar datos adicionales propuestos según el modelo utilizado, tales como:
Población por manzana.
Ingresos promedio.
Densidad de viviendas.
Ejecutar un script .sql que contenga:
Procesos de cálculo de distancias geográficas.
Identificación de centroides para cada predio.
Cálculo ponderado considerando densidad poblacional.
Identificación de las ubicaciones óptimas.
Guardar los resultados en un esquema de salida en la base de datos.
Salida del Proyecto
El proyecto genera los siguientes resultados:

Un esquema de resultados en la base de datos con la información procesada.
La ubicación geométrica (“geom”) de la farmacia con menor distancia ponderada.
Estructura del Repositorio
├── Entradas/                # Carpeta con datos de entrada (capas espaciales, predios, etc.).
├── sql_queries/             # Archivos SQL necesarios para los procesos.
├── codigo.py                # Script principal en Python.
├── config                   # Configuración de conexión a la base de datos.
├── README.md                # Este archivo.
Requisitos de Entrega
Crear un repositorio en GitHub que incluya:
Un archivo README.md con instrucciones claras sobre cómo clonar y ejecutar el proyecto en local.
Instrucciones para instalar dependencias y configurar el entorno.
Archivos SQL necesarios para los procesos.
Script Python bien documentado.
Datos de ejemplo para poblar la base de datos y probar el proyecto.
Ejemplo de uso y resultados generados.
Instrucciones de Ejecución
1. Configurar el Entorno
Instalar PostgreSQL y PostGIS.
Descomprimir la base de datos
Configurar el archivo config con los parámetros de conexión a la base de datos.
2. Instalar Dependencias
Se recomienda crear un entorno virtual e instalar las dependencias:

python -m venv env
source env/bin/activate  # En Windows: env\Scripts\activate
pip install -r requirements.txt
3. Poblar Datos
Asegúrate de cargar los datos iniciales desde la carpeta Entradas/ a la base de datos.
Ejecuta el script principal:
python codigo.py
4. Resultados
Los resultados se almacenarán en el esquema salida de la base de datos y podrán consultarse desde herramientas como pgAdmin o mediante scripts SQL adicionales.

Ejemplo de Scripts
Un ejemplo de los scripts SQL utilizados está disponible en la carpeta sql_queries/. Incluyen:

Cálculo de centroides.
Cálculo de distancias geográficas.
Ponderación de distancias según densidad poblacional.
Selección de la ubicación óptima para las farmacias.
Modelo Utilizado
El modelo utilizado para determinar la ubicación óptima considera:

Distancias mínimas entre los centroides de los predios de menor nivel socioeconómico y las posibles ubicaciones de farmacias.
Densidad poblacional como factor de ponderación.
Criterios espaciales derivados de las capas de entrada y las normativas asociadas.
Contacto
Para dudas o consultas, contacta a kurt.gee@usach.cl/Kurt2Gee.
