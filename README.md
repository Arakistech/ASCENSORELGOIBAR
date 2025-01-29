# ASCENSORELGOIBAR
Este es el Gemelo Digital de los ascensores/escaleras mecánicas Elgoibar.

Se puede acceder vía en siguiente enlace web: https://imhdynamics.cloud/

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Ascensor2.gif?raw=true" width="800" height="480">


# Captura de datos 

La captura de datos se ha realizado en las proximidades del IMH de Elgoibar. Pulsando sobre la siguiente imagen se puede acceder al mapa interactivo de la zona.


<a href="https://arakistech.github.io/Castilla/#17.5/43.211867/-2.411639/-124/53"> <img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/mapa.jpg?raw=true" alt="Click me!" width="800" height="400" /> </a>

El hardware empleado para la captura de datos está basado en el acelerómetro ICM-42688... (describir)

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Acelerometro.jpeg?raw=true" width="800" height="400">

Y una APP móvil para Android que se encarga del registro de los datos. 

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/vibraciones.png?raw=true" width="1000" height="250">


# Comunicación de datos

## 1. Crear API de Google Sheet

>> **Acceder a Google Cloud**: [Click aquí!](https://console.cloud.google.com/welcome?authuser=1&hl=es&inv=1&invt=Abnbrw&project=weighty-fabric-448414-r0)

    1.01 Seleccionar APIs y servicios
    1.02 Seleccionar HABILITAR APIS Y SERVICIOS
    1.03 Busca Google Sheets API y selecciona
    1.04 Selecciona Habilitar
    1.05 Seleccionar Credenciales (después de CUOTAS Y LÍMITES DEL SISTEMA)
    1.06 Seleccionar + CREAR CREDENCIALES
    1.07 Seleccionar Cuenta de Servicio
    1.08 Añadir un nombre y seleccionar Crear y continuar
    1.09 Seleccionar Rol: Editor, continuar y Listo
    1.10 En la opción de credenciales, mirar cuentas de servicio
    1.11 Selecionar editar (icono lapiz)
    1.12 Seleccionar Claves
    1.13 Agregar clave: Crear Clave nueva
    1.14 Seleccionar JSON y se descarga

## 2. Crear Google Sheet y compartir a correo electronico

    1.15 Crear un google sheet donde quieras.
    1.16 Compartir y dar acceso de editor al correo electronico que sale en credenciales (paso 1.10)
<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/acceso%20a%20correo%20electronico.png">


## 3. Preparar Node-RED

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Flujo2_Node-RED.png">

    1.17 Instalar un nodo o extensión llamado node-red-contrib-google-sheets
        > (tres lineas juntos)/administrar paleta/(al lado del nodo seleccionar instalar)
    1.18 Buscar bloques en el panel de nodos (a la izquierda de la pantalla)
    1.19 Copia exactamente igual que la primera fila de bloques mostrado en la imagen de arriba
    1.20 Doble click en Gsheet para acceder a su propiedad (siguiente imagen)

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Editar%20Nodo%20GSheet.png">

    1.21 En `creds` seleccionar el icono del lapiz
    1.22 Pegar los datos JSON obtenido anteriormente (TODO) - (siguiente imagen)

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/EditarNodoGauth.png">

    1.23 En `Method` elegir Append Row
    1.24 En `SpreadsheetID` Pegar el ID que se encuentra en el enlace (URL) de Google Sheet

>> **URL del Google Sheet**: `https://docs.google.com/spreadsheets/d/     > SpreadsheetID <     /edit?gid=0#gid=0`

    1.25 En `Cells` Debes poner la hoja y el rango de Google Sheet.
         El nombre de la hoja debe ser EXACTO!!

## 4. Prueba de comunicación entre Node-RED y Google Sheet

    1.26 Al seleccionar en el boton que se encuentra a la izquierda del bloque de `marca tiempo`
         de Node-RED, enviará un tiempo que se debería registrarse en en el Google Sheet

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Google%20Sheet%20-%20Ascensor.png">

# Base de datos
2 Tipos de bases de datos: relacionales y no relacionales. 
  1. Relacionales (EJ SQL): Es necesario que los datos tengan una estructura predeterminada al crear las tablas. En caso de que los datos no cumplan los requisitos no se graban.
  2. No relacionales (EJ MongoDB): No es necesario que tengan una estructura definida. Usada cuando no esta clara la     relacion de los datos a almacenar.
 
  
  Añadir datos a la base de datos de las escaleras mecanicas a influxDB (base de datos especializada en Series temporales): 

  Requisitos y estructura necesaria para subir .csv a InfluxDB. InfluxDB demanda una estructura y una información muy especifica para subir un archivo .csv. Por lo que las especificaciones son las siguientes:
  1. Primera fila del .csv indica el tipo de dato en esa columna. [time, measurement, field, tag]
       1.1 Time: marca del tiempo (debe seguir la ISO8601 --> *YYYY-MM-DDTHH:mm:ssZ* ó en segundos totales desde 1970 denominado UNIX )
       1.2 Measurement: metrica o unidad de la columna.
       1.3 Field: Valores numericos o cadenas.
       1.4 Tag: Categorias.
  3. Segunda linea contiene las cabeceras de las columnas. 
  4. Los valores deben dividirse por comas.
  5. Crear un bucket en InfluxDB
  6. Arrastrando el archivo .csv al bucket "Practica ASCENSOR ELGOIBAR" se añade la información del csv al bucket. 
  

https://jaksv.medium.com/how-to-upload-a-csv-file-to-influxdb-2-0-238b4f1015e5

# Detección de anomalías


# Visualización de datos

- https://public.tableau.com/views/Iara_16387319222540/MODIFICADOIVAN?:showVizHome=no#1

- Análisis Ascensor Ermua: [Tableu Dashboard](https://public.tableau.com/app/profile/jae.alkorta/viz/AnalisisascensorErmua/Dashboard1?publish=yes)
- Análisis Escaleraa Elgoibar: [Tableu Dashboard](poner link nico)

- Otro tipo de visualización https://public.tableau.com/app/profile/david.joel.rodriguez.saravia/viz/Ascensores_prueba/Hoja1?publish=yes
- Análisis de Ascensor Tiempo de anomalias/elevador/recuento de personas: https://public.tableau.com/app/profile/david.joel.rodriguez.saravia/viz/AnlisisAscensoresErmuaTiempo_de_anomalias_elevador_recuento_de_personas/Hoja1?publish=yes

- ![Escalera - Prueba 1](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%201.png)
- ![Escalera - Prueba 2](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%202.png)
- ![Escalera - Prueba 3](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%203.png)
- ![Escalera - Prueba 4](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%204.png)
- ![Ventilador - Prueba 1](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%201.png)
- ![Ventilador - Prueba 2](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%202.png)
- ![Ventilador - Prueba 3](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%203.png)
- ![Ventilador - Prueba 4](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%204.png)





