# ANÁLISIS DE VIBRACIONES EN LOS ASCENSORES/ESCALERAS MECÁNICAS DE  ELGOIBAR
Este es el Gemelo Digital de los ascensores/escaleras mecánicas Elgoibar.

Se puede acceder vía en siguiente enlace web: https://imhdynamics.cloud/

Puede solicitar acceso a la plataforma web mediante usuario y clave, poniéndose en contacto con nosotros. 

<img src="https://github.com/Arakistech/ASCENSORELGOIBAR/blob/main/IMG/Ascensor2.gif?raw=true" width="800" height="480">

# Principio de funcionamiento del mantenimiento predictivo
El mantenimiento predictivo es una estrategia avanzada que emplea tecnología y análisis de datos para anticipar y prevenir fallos en equipos y maquinaria, optimizando su rendimiento y vida útil.

Esta práctica es fundamental para las empresas, ya que minimiza costos y tiempos de inactividad al evitar fallos inesperados. En entornos de alta demanda, las organizaciones que aplican mantenimiento predictivo pueden garantizar una producción continua y eficiente, mejorando la disponibilidad de sus recursos y optimizando la operatividad del sistema.

- **Recopilación de datos**: Se obtienen mediciones en tiempo real a través de sensores IoT y dispositivos de monitoreo instalados en los equipos. Por ejemplo Temperatura, Vibraciones, Humedad, Presión y Sonido.

- **Transmisión y almacenamiento**: Los datos recopilados se envían a sistemas de almacenamiento en la nube o bases de datos locales para su posterior procesamiento.

![Diagrama básico con sistema SCADA](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/Sistema%20SCADA.png)


- **Análisis de datos**: Se aplican algoritmos de inteligencia artificial y técnicas de análisis predictivo para identificar patrones y señales que indiquen posibles fallos. 

- **Generación de insights y acción**: A partir del análisis, se generan alertas y recomendaciones que permiten tomar decisiones informadas para el mantenimiento y la optimización del rendimiento de los equipos.

![Dashboard: Análisis, límites y alertas](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/SPC%20gr%C3%A1fico.png)

## Análisis de vibraciones

El análisis de vibraciones en el dominio del tiempo es una herramienta crucial para el mantenimiento predictivo en la industria moderna. Este método permite:

### Análisis de vibraciones en el dominio del tiempo

- **Detección temprana de fallos**: Identifica cambios sutiles en el comportamiento de la maquinaria que pueden indicar problemas potenciales.
- **Mejora de la seguridad y fiabilidad**: Ayuda a prevenir fallos graves, reduciendo riesgos para el personal y el entorno.
- **Reducción de costos**: Minimiza el tiempo de inactividad no planificado y los costos de mantenimiento.
- **Optimización de programas de mantenimiento**: Permite pasar de un mantenimiento reactivo a uno basado en la condición real del equipo.

### Características clave del análisis
El análisis de vibraciones en el dominio del tiempo implica:

- **Representación de la señal temporal**: Muestra la amplitud de la vibración en función del tiempo.
- **Análisis del historial temporal**: Examina la forma de onda para identificar características como respuesta transitoria y resonancia.
- **Medidas estadísticas**: Incluye valores pico, RMS y factor de cresta para cuantificar la intensidad de la vibración.

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
-Aquí se muestra las imágenes de las ubicación de los 3 ascensores de Ermua 
-
- Análisis de Ascensor Tiempo de anomalias/elevador/recuento de personas:
-Aquí se muestra una gráfica de los ascensores de Ermua donde se muestra la relación entre el tiempo de anomalías el elevador y el recuento de personas
- https://public.tableau.com/app/profile/david.joel.rodriguez.saravia/viz/AnlisisAscensoresErmuaTiempo_de_anomalias_elevador_recuento_de_personas/Hoja1?publish=yes

- ![Escalera - Prueba 1](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%201.png)
- ![Escalera - Prueba 2](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%202.png)
- ![Escalera - Prueba 3](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%203.png)
- ![Escalera - Prueba 4](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%204.png)
- Interpretación de los gráficos de la escalera:
1. Aceleración vs Tiempo (Gráfico Izquierdo)
Se presentan las tres componentes de aceleración (acc_x, acc_y, acc_z) en función del tiempo.
La señal parece bastante estable, con pequeñas variaciones alrededor de ciertos valores constantes.
Esto sugiere que la escalera mecánica no tiene grandes vibraciones ni movimientos bruscos, aunque existen pequeñas oscilaciones.
La aceleración en cada eje representa el comportamiento del movimiento en la dirección correspondiente. Por ejemplo, si el sensor estaba orientado correctamente, 
acc_z podría reflejar la gravedad, mientras que acc_x y acc_y representarían movimientos laterales o longitudinales.

2. Transformada Rápida de Fourier (FFT) (Gráfico Central)
Este gráfico descompone la señal en sus componentes de frecuencia, mostrando qué frecuencias están más presentes en la vibración.
Se observa un pico claro alrededor de los 7 Hz en el eje acc_z (azul), lo que indica que existe una vibración dominante en esa frecuencia.
Frecuencias más bajas y distribuidas en acc_x y acc_y pueden estar relacionadas con el movimiento mecánico general de la escalera, mientras que el pico en acc_z podría deberse a la vibración generada por el motor o los mecanismos de soporte.
3. Densidad Espectral de Potencia (PSD) (Gráfico Derecho)
Este gráfico muestra cómo la potencia de la señal está distribuida en las diferentes frecuencias.
La curva roja (acc_x) tiene más energía en las bajas frecuencias, lo cual es común en estructuras mecánicas con oscilaciones de baja frecuencia.
La curva azul (acc_z) tiene más fluctuaciones y caída de energía a mayores frecuencias, lo que podría indicar la presencia de ruido o vibraciones de alta frecuencia menos persistentes.
La curva verde (acc_y) sigue una tendencia intermedia, lo que sugiere que la vibración en este eje es menos intensa que en acc_z, pero sigue presente en bajas frecuencias.
- ![Ventilador - Prueba 1](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%201.png)
- ![Ventilador - Prueba 2](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%202.png)
- ![Ventilador - Prueba 3](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%203.png)
- ![Ventilador - Prueba 4](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Ventilador%20-%20Prueba%204.png)
1. Aceleración vs Tiempo (Gráfico Izquierdo)
Se observa una oscilación muy regular en la aceleración acc_z (azul), lo que indica un movimiento periódico, característico de un ventilador en funcionamiento.
La amplitud de acc_z es mucho mayor que la de acc_x y acc_y, lo que sugiere que la vibración más fuerte ocurre en la dirección vertical. Esto puede deberse a un desbalanceo en las aspas o el motor. También se aprecian oscilaciones en acc_x y acc_y, aunque de menor magnitud, lo que indica que hay cierta vibración en las direcciones horizontal y lateral, probablemente por las fuerzas aerodinámicas o pequeños desajustes en la estructura.

2. Transformada Rápida de Fourier (FFT) (Gráfico Central)
Aparece un pico muy marcado cerca de los 5 Hz, lo que indica que esta es la frecuencia principal de vibración del ventilador. Esta frecuencia podría corresponder a la frecuencia de giro del rotor. Si el ventilador tiene 5 Hz como frecuencia dominante, significa que está girando a aproximadamente 300 RPM (revoluciones por minuto), ya que:
5 Hz×60 s/min=300 RPM
También se ve un segundo pico cerca de los 10 Hz, que puede ser un armónico, lo que sugiere que hay una resonancia secundaria posiblemente causada por la interacción con la estructura o el soporte del ventilador.

3. Densidad Espectral de Potencia (PSD) (Gráfico Derecho)
La PSD confirma que la mayor parte de la energía de la vibración se encuentra en 5 Hz, reforzando que esta es la frecuencia fundamental de operación del ventilador.
La curva azul (acc_z) tiene el mayor valor en esta frecuencia, lo que indica que la vibración más intensa ocurre en la dirección vertical.acc_x y acc_y también tienen picos en la misma frecuencia, pero con menor potencia, lo que sugiere que hay vibraciones en todos los ejes, aunque menos intensas en las direcciones laterales.
El aumento de la energía en bajas frecuencias podría deberse a pequeñas irregularidades en el motor o el montaje del ventilador.





