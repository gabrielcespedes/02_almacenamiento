# Clase 02 - Soluciones de Almacenamiento de Datos

Este repositorio contiene los ejercicios realizados en clase sobre la conexión y manipulación de datos en la nube utilizando **Microsoft Azure** y **Google Cloud Platform (GCP)**.

## Estructura del Ejercicio

El proyecto se divide principalmente en dos entornos de trabajo que abordan las APIs de almacenamiento en la nube:

### 1. Microsoft Azure (`azure/azure.ipynb`)
Este notebook de Jupyter demuestra un flujo completo de trabajo con **Azure Blob Storage / Data Lake Storage**.
*   **Conexión**: Se utiliza `BlobServiceClient` para autenticarse usando una cadena de conexión almacenada de forma segura en un archivo local (`key.txt`).
*   **Gestión de Contenedores**: Creación de un contenedor denominado `zona-bronze`.
*   **Carga de Archivos (Upload)**: Subida de archivos CSV locales hacia rutas jerárquicas dentro del Data Lake (ej. `raw/ventas/2026/07/sales.csv`).
*   **Exploración**: Listado de los blobs contenidos en el contenedor.
*   **Descarga de Datos**: Recuperación de archivos desde la nube hacia el almacenamiento local.
*   **Desafío Práctico**: Un script automatizado que recorre archivos locales, lee sus metadatos (fecha de modificación) y los sube a Azure distribuyéndolos en carpetas jerárquicas (`año/mes/día/`). Incluye manejo de errores, lógica de reintentos ante problemas de red y un sistema de registro de eventos (logging).

### 2. Google Cloud Platform (`gcp/gcp.ipynb`)
Este notebook es una introducción a la conexión con **Google Cloud Storage (GCS)**.
*   **Conexión Cliente GCS**: Configuración y autenticación inicial utilizando un archivo de credenciales de cuenta de servicio (`account.json`). El script valida la existencia del archivo de forma segura y define la variable de entorno `GOOGLE_APPLICATION_CREDENTIALS` antes de instanciar el cliente de Storage.

## Requisitos y Configuración

Para ejecutar estos notebooks correctamente, es necesario proveer las credenciales de los proveedores de nube, las cuales **no deben exponerse** en el código fuente.

*   Para **Azure**: Crear un archivo llamado `key.txt` dentro de la carpeta `azure/` que contenga únicamente tu *Connection String*.
*   Para **GCP**: Descargar tu clave de cuenta de servicio en formato JSON, renombrarla a `account.json` y guardarla dentro de la carpeta `gcp/`.


