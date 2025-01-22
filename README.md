# ASCENSORELGOIBAR
Gemelo Digital Ascensor/escaleras mecánicas Elgoibar



# Captura de datos 
<a href="https://arakistech.github.io/Castilla/#17.5/43.211867/-2.411639/-124/53"> <img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/mapa.jpg?raw=true" alt="Click me!" width="800" height="400" /> </a>


<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Acelerometro.jpeg?raw=true" width="800" height="400">


<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/vibraciones.png?raw=true" width="1000" height="250">


# Comunicación de datos

## 1. Crear API de Google Sheet

>> **Acceder a Google Cloud**: [Click aquí!](https://console.cloud.google.com/welcome?authuser=1&hl=es&inv=1&invt=Abnbrw&project=weighty-fabric-448414-r0)

    1.1 Seleccionar APIs y servicios
    1.2 Seleccionar HABILITAR APIS Y SERVICIOS
    1.3 Busca Google Sheets API y selecciona
    1.4 Selecciona Habilitar
    1.5 Seleccionar Credenciales (después de CUOTAS Y LÍMITES DEL SISTEMA)
    1.6 Seleccionar + CREAR CREDENCIALES
    1.7 Seleccionar Cuenta de Servicio
    1.8 Añadir un nombre y seleccionar Crear y continuar
    1.9 Seleccionar Rol: Editor, continuar y Listo
    2.0 En la opción de credenciales, mirar cuentas de servicio
    2.1 Selecionar editar (icono lapiz)
    2.2 Seleccionar Claves
    2.3 Agregar clave: Crear Clave nueva
    2.4 Seleccionar JSON y se descarga

## 2. Crear Google Sheet y compartir a correo electronico

    2.5 Crear un google sheet donde quieras.
    2.6 Compartir y dar acceso de editor al correo electronico que sale en credenciales (paso 2.0)

## 3. Preparar Node-RED

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Flujo2_Node-RED.png" width="800" height="500">

    2.1 Instalar un nodo o extensión llamado node-red-contrib-google-sheets
        - (tres lineas juntos)/administrar paleta/(al lado del nodo seleccionar instalar)
    2.2 Buscar bloques en el panel de nodos (a la izquierda de la pantalla)
    2.3 Copia exactamente igual que la primera fila de bloques mostrado en la imagen de arriba
    2.4 Doble click en Gsheet para acceder a su propiedad (siguiente imagen)
<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Editar%20Nodo%20GSheet.png" width="800" height="500">



# Base de datos
2 Tipos de bases de datos: relacionales y no relacionales. 
  1. Relacionales (EJ SQL): Es necesario que los datos tengan una estructura predeterminada al crear las tablas. En caso de que los datos no cumplan los requisitos no se graban.
  2. No relacionales (EJ MongoDB): No es necesario que tengan una estructura definida. Usada cuando no esta clara la     relacion de los datos a almacenar.
 
  
  Añadir datos a la base de datos de las escaleras mecanicas a influxDB (base de datos especializada en Series temporales): 

  Requisitos y estructura necesaria para subir .csv a InfluxDB. InfluxDB demanda una estructura y una información muy especifica para subir un archivo .csv. Por lo que las especificaciones son las siguientes:
  1. Primera fila del .csv indica el tipo de dato en esa columna. [time, measurement, field, tag]
       1.1 Time: marca del tiempo (debe seguir la ISO8601 --> *YYYY-MM-DDTHH:mm:ssZ* ó en segundos totales)
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
  
