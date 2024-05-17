<h1 style="color: #004286; font-family: 'Arial', sans-serif;">Google-photos-image-search</h1>

Este documento proporciona una guía detallada del funcionamiento del buscador de imágenes de Google Photos con procesamiento de lenguaje natural. La aplicación permite buscar imágenes descargadas de Google Photos y visualizarlas en una interfaz gráfica, todo ello basado en las palabras clave ingresadas por el usuario. Se emplean técnicas de procesamiento de lenguaje natural para refinar las consultas, mientras que un modelo de detección de objetos se encarga de identificar los objetos presentes en las imágenes.

## Requisitos Previos

Antes de comenzar con la configuración de la aplicación de búsqueda de imágenes, asegúrate de tener acceso a las siguientes cuentas y herramientas, y disponer de las credenciales necesarias:

1. **Python 3.7 o superior**
   - **Descripción**: La aplicación está desarrollada en Python y requiere la versión 3.7 o superior para su funcionamiento adecuado.
   - **Instalación**: Si aún no tienes Python instalado en tu sistema, puedes descargarlo e instalarlo desde [python.org](https://www.python.org/downloads/). Asegúrate de seleccionar la versión compatible con tu sistema operativo.

2. **Bibliotecas de Python**
   - **Descripción**: La aplicación hace uso de varias bibliotecas de Python para realizar diferentes tareas, como el procesamiento de imágenes y texto, la autenticación con la API de Google Photos, entre otros.
   - **Instalación**: Para instalar las bibliotecas requeridas, puedes utilizar el gestor de paquetes pip ejecutando el siguiente comando en tu terminal:
     ```bash
     pip install torch pillow nltk google-auth-oauthlib google-auth requests
     ```

3. **Recursos de NLTK**
   - **Descripción**: NLTK (Natural Language Toolkit) es una biblioteca de Python ampliamente utilizada en el procesamiento del lenguaje natural. La aplicación requiere ciertos recursos específicos de NLTK, como las listas de stopwords y los datos de lematización (wordnet), para realizar el filtrado de consultas de manera efectiva.
   - **Descarga**: Antes de ejecutar la aplicación, asegúrate de descargar estos recursos ejecutando el siguiente código en un script de Python o en un entorno interactivo:
     ```python
     import nltk
     nltk.download('stopwords')
     nltk.download('wordnet')
     ```

4. **Configuración de Google Photos API**
   - **Descripción**: Para acceder y obtener las imágenes desde Google Photos, es necesario configurar una cuenta en Google Cloud y habilitar la API de Google Photos Library para tu proyecto.
   - **Pasos**:
     1. **Crear un Proyecto en Google Cloud Console:** Accede a Google CloudConsole [Google Cloud Console](https://console.cloud.google.com/) y crea un proyecto
     2. **Habilitar la API de Google Photos Library:** En la sección "API y servicios", busca y habilita la API de Google Photos Library para tu proyecto.
      3. **Obtener Credenciales de API:** Configura las credenciales OAuth 2.0 y descarga el archivo JSON de credenciales proporcionado por Google.
     4. **Guardar y Renombrar el Archivo de Credenciales:** Guarda el archivo JSON de credenciales en el directorio raíz de tu proyecto y asegúrate de renombrarlo como `client_secret.json`.

5. **Archivo de Configuración**
   - **Descripción**: La aplicación utiliza un archivo de configuración llamado config.json para almacenar la ruta del archivo de credenciales de Google Photos API.
     ```json
     {
       "client_secret_file": "ruta/al/archivo/client_secret.json"
     }
     ```

# Cómo Ejecutar la Aplicación

## Paso 1: Descargar Imágenes de Google Photos

- **Inicio de la Aplicación:** Ejecuta el script principal de la aplicación. Esto puede hacerse desde la terminal con el siguiente comando:

  ```bash
  python tu_proyecto.py
  ```
  
  - **Autenticación en Google:** Al iniciar la aplicación, se te pedirá que inicies sesión en tu cuenta de Google. Sigue las instrucciones en la terminal y proporciona tus credenciales de Google cuando se te solicite.

- **Aceptación de Acceso:** Después de iniciar sesión, es posible que se te pida que otorgues permiso a la aplicación para acceder a tu cuenta de Google Photos. Revisa los permisos solicitados y acepta para que la aplicación pueda descargar tus fotos.

- **Descarga de Imágenes:** Una vez que hayas iniciado sesión y otorgado permiso, la aplicación comenzará a descargar las imágenes de tu cuenta de Google Photos. Este proceso puede tardar un poco dependiendo de la cantidad de imágenes que tengas en tu biblioteca.

## Paso 2: Introducir Consultas de Búsqueda

- **Terminal Interactiva:** Una vez que se complete la descarga de imágenes, aparecerá una terminal interactiva en la que podrás introducir tus consultas de búsqueda.

- **Introduce tus Consultas:** Escribe las palabras clave o frases que deseas buscar en tus imágenes y presiona Buscar. La aplicación procesará tus consultas y buscará imágenes relevantes en función de tus criterios de búsqueda.

## Paso 3: Visualización de Resultados

- **Visualización en la Interfaz Gráfica:** Después de procesar tus consultas, la aplicación mostrará las imágenes coincidentes en una interfaz gráfica. Puedes explorar las imágenes y ver los resultados de tu búsqueda directamente en la interfaz de usuario.

## Autor: 
<span style="font-size: smaller;">Andrea Hernando González</span>
