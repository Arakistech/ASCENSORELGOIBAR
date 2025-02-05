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

El análisis de vibraciones es una técnica fundamental en el mantenimiento predictivo industrial. Proporciona información crucial sobre el estado y rendimiento de las máquinas, permitiendo detectar problemas antes de que causen fallos graves.

![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/Vibration%20Analysis%20Data%20in%20Detail_.jpg)

### Principales beneficios del análisis de vibraciones en dominio temporal
El análisis de vibraciones en el dominio del tiempo examina cómo varía la amplitud de la vibración a lo largo del tiempo. Esta técnica ofrece una visión general del comportamiento vibratorio de la máquina y puede revelar eventos anormales que no siempre son evidentes en otros tipos de análisis.

![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/Time-Domain%20Vibration%20Analysis%20and%20its%20importance.jpg)

### Beneficios clave
- Detección temprana de fallos
- Mejora de la seguridad operativa
- Reducción de costos de mantenimiento
- Minimización de paradas no planificadas
- Optimización de estrategias de mantenimiento
- Evaluación precisa del rendimiento de la maquinaria

### Características clave del análisis

La señal de vibración se representa como una forma de onda, mostrando la amplitud de la vibración en función del tiempo. Esta representación permite identificar patrones y anomalías en el comportamiento vibratorio de la máquina.

![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/Information%20Provided%20by%20Time-Domain%20Vibration%20Analysis.jpg)

Parámetros importantes

![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/IMG/Peak%2C%20RMS%2C%20and%20Crest%20Factor.jpg)

- **Pico**: Valor máximo de la amplitud de vibración
- **RMS (Root Mean Square)**: Medida de la energía contenida en la vibración
- **Factor de Cresta**: Relación entre el valor pico y el RMS, útil para detectar impactos

### Análisis estadístico
Se utilizan medidas estadísticas como la desviación estándar, la curtosis y la asimetría para caracterizar la distribución de la vibración en el tiempo.

### Análisis en el dominio de la frecuencia
Complementa el análisis temporal, descomponiendo la señal en sus frecuencias constituyentes. Utiliza la Transformada Rápida de Fourier (FFT) para convertir la señal del dominio del tiempo al dominio de la frecuencia.

### Análisis conjunto tiempo-frecuencia
Técnicas como Gabor-Wigner-Wavelet permiten analizar cómo varían las frecuencias de vibración a lo largo del tiempo.

### Sensores y adquisición de datos
La selección de sensores adecuados es crucial. Los acelerómetros son los más comunes, pero también se utilizan sensores láser de alta velocidad para mediciones sin contacto. Características deseables en los sensores incluyen:

- Alta resolución de datos
- Múltiples modos de operación
- Precisión elevada
- Larga duración de la batería
- Capacidades inalámbricas para facilitar la instalación y el mantenimiento

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

En el caso especifico de los datos de vibraciones, el time está en segundos con fracciones. En tiempo absoluto. Para cambiar este campo a ISO8601 (el formato requerido por IfluxDB) hemos usado el siguiente script de Phyton: 

    from datetime import datetime, timedelta

    # Fecha y hora inicial
    start_time = datetime(2025, 1, 20, 15, 0)
    
    # Lista de segundos proporcionada (valores decimales)
    seconds_list = [
        0, 0.040604651, 0.081209302, 0.121813953, 0.162418605, 0.203023256, 0.243627907, 
        0.284232558, 0.324837209, 0.36544186, 0.406046512, 0.446651163, 0.487255814, 
        0.527860465, 0.568465116, 0.609069767, 0.649674419, 0.69027907, 0.730883721, 
        0.771488372, 0.812093023, 0.852697674, 0.893302326, 0.933906977, 0.974511628, 
        1.015116279, 1.05572093, 1.096325581, 1.136930233, 1.177534884, 1.218139535, 
        1.258744186, 1.299348837, 1.339953488, 1.38055814, 1.421162791, 1.461767442, 
        1.502372093, 1.542976744, 1.583581395, 1.624186047, 1.664790698, 1.705395349, 
        1.746, 1.786604651, 1.827209302, 1.867813953, 1.908418605, 1.949023256, 
        1.989627907, 2.030232558, 2.070837209, 2.11144186, 2.152046512, 2.192651163, 
        2.233255814, 2.273860465, 2.314465116, 2.355069767, 2.395674419, 2.43627907, 
        2.476883721, 2.517488372, 2.558093023, 2.598697674, 2.639302326, 2.679906977, 
        2.720511628, 2.761116279, 2.80172093, 2.842325581, 2.882930233, 2.923534884, 
        2.964139535, 3.004744186, 3.045348837, 3.085953488, 3.12655814, 3.167162791, 
        3.207767442, 3.248372093, 3.288976744, 3.329581395, 3.370186047, 3.410790698, 
        3.451395349, 3.492, 3.532604651, 3.573209302, 3.613813953, 3.654418605, 
        3.695023256, 3.735627907, 3.776232558, 3.816837209, 3.85744186, 3.898046512, 
        3.938651163, 3.979255814, 4.019860465, 4.060465116, 4.101069767, 4.141674419, 
        4.18227907, 4.222883721, 4.263488372, 4.304093023, 4.344697674, 4.385302326, 
        4.425906977, 4.466511628, 4.507116279, 4.54772093, 4.588325581, 4.628930233, 
        4.669534884, 4.710139535, 4.750744186, 4.791348837, 4.831953488, 4.87255814, 
        4.913162791, 4.953767442, 4.994372093, 5.034976744, 5.075581395, 5.116186047, 
        5.156790698, 5.197395349, 5.238, 5.278604651, 5.319209302, 5.359813953, 
        5.400418605, 5.441023256, 5.481627907, 5.522232558, 5.562837209, 5.60344186, 
        5.644046512, 5.684651163, 5.725255814, 5.765860465, 5.806465116, 5.847069767, 
        5.887674419, 5.92827907, 5.968883721, 6.009488372, 6.050093023, 6.090697674, 
        6.131302326, 6.171906977, 6.212511628, 6.253116279, 6.29372093, 6.334325581, 
        6.374930233, 6.415534884, 6.456139535, 6.496744186, 6.537348837, 6.577953488, 
        6.61855814, 6.659162791, 6.699767442, 6.740372093, 6.780976744, 6.821581395, 
        6.862186047, 6.902790698, 6.943395349, 6.984, 7.024604651, 7.065209302, 
        7.105813953, 7.146418605, 7.187023256, 7.227627907, 7.268232558, 7.308837209, 
        7.34944186, 7.390046512, 7.430651163, 7.471255814, 7.511860465, 7.552465116, 
        7.593069767, 7.633674419, 7.67427907, 7.714883721, 7.755488372, 7.796093023, 
        7.836697674, 7.877302326, 7.917906977, 7.958511628, 7.999116279, 8.03972093, 
        8.080325581, 8.120930233, 8.161534884, 8.202139535, 8.242744186, 8.283348837, 
        8.323953488, 8.36455814, 8.405162791, 8.445767442, 8.486372093, 8.526976744, 
        8.567581395, 8.608186047, 8.648790698, 8.689395349, 8.73, 8.770604651, 
        8.811209302, 8.851813953, 8.892418605, 8.933023256, 8.973627907, 9.014232558, 
        9.054837209, 9.09544186, 9.136046512, 9.176651163, 9.217255814, 9.257860465, 
        9.298465116, 9.339069767, 9.379674419, 9.42027907, 9.460883721, 9.501488372, 
        9.542093023, 9.582697674, 9.623302326, 9.663906977, 9.704511628, 9.745116279, 
        9.78572093, 9.826325581, 9.866930233, 9.907534884, 9.948139535, 9.988744186, 
        10.02934884, 10.06995349, 10.11055814, 10.15116279, 10.19176744, 10.23237209, 
        10.27297674, 10.3135814, 10.35418605, 10.3947907, 10.43539535
    ]
    
    # Función para convertir segundos a fecha ISO8601 con decimales
    def convert_seconds_to_iso8601(seconds_list):
        result = []
        for seconds in seconds_list:
            # Calcular la nueva fecha sumando los segundos (decimales) a la fecha inicial
            new_time = start_time + timedelta(seconds=seconds)
            # Crear el formato ISO8601 manteniendo los decimales
            formatted_time = new_time.strftime('%Y-%m-%dT%H:%M:%S') + f'.{int(seconds*1000000):06d}Z'
            result.append(formatted_time)
        return result
    
    # Convertir los registros
    iso8601_dates = convert_seconds_to_iso8601(seconds_list)
    
    # Mostrar resultados
    for date in iso8601_dates:
        print(date)




        mediante el script se han convertido los segundos en fechas ISO8601, partiendo como fecha de inicio el 20 de enero de 2025 a las 15:00.

# Detección de anomalías

Para la detección de anomalias se usa Edge Impulse.

Después de la creación del proyecto:

1. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Conectar%20dispositivo.png)
2. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/escanear%20con%20el%20movil.png)
3. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/registrar%20datos.png)
4. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Crear%20impulse.png)
5. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/usando%20el%20modelo%20entrenarlo.png)
6. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/usando%20el%20modelo%20entrenarlo%202.png)
7. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Reentrenar.png)
8. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/ponerlo%20a%20prueba%20con%20una%20nueva.png)

Los datos usados se encuentran en la carpeta Edge Impulse:
## Clasificar tipos de vibraciones



## Contar cantidad de personas y si es mujer u hombre
1. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Detectar%20imagenes/Screenshot%202025-02-04%20at%2016-46-58%20Fomo%20-%20Live%20classification%20-%20Edge%20Impulse%20-%20testing.5j5essko.png)
2. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Detectar%20imagenes/Screenshot%202025-02-04%20at%2016-47-25%20Fomo%20-%20Live%20classification%20-%20Edge%20Impulse%20-%20testing.5j5essko.png)
3. ![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Edge%20Impulse/Detectar%20imagenes/Screenshot%202025-02-04%20at%2016-47-33%20Fomo%20-%20Live%20classification%20-%20Edge%20Impulse%20-%20testing.5j5essko.png)

# Visualización de datos

### Realidad Aumentada

- https://jaealkorta.github.io/Realidad_Aumentada/
- https://aitorruizp.github.io/3D-Scalator/index.html


### Qucs Software

![alt text](https://raw.githubusercontent.com/Arakistech/ASCENSORELGOIBAR/refs/heads/main/Circuito%20Electrico/Circuito%20Electrico%20simple.png)

### Tableu Public

- https://public.tableau.com/views/Iara_16387319222540/MODIFICADOIVAN?:showVizHome=no#1

- Análisis Ascensor Ermua: [Tableu Dashboard](https://public.tableau.com/app/profile/jae.alkorta/viz/AnalisisascensorErmua/Dashboard1?publish=yes)


- Análisis Escaleraa Elgoibar: [Tableu Dashboard](poner link nico)

Gráfico del Eje Z:
El valor cercano a 100 millones podría estar relacionado con un evento puntual generado por el impacto de una persona o salto brusco.
Dicha magnitud sugiere que el eje vertical es muy sensible a fuerzas externas. Esta sensibilidad puede ser un factor a evaluar para sistemas que requieran estabilidad en el eje Z.
Para reducir estos picos, sería recomendable mejorar el aislamiento de la máquina respecto al entorno.
Gráfico del Eje Y:
La amplitud negativa cercana a -400 mil podría también ser consecuencia de un salto, pero con una menor intensidad en comparación con el eje Z.
El eje Y tiende a captar vibraciones horizontales, lo que sugiere que el impacto del salto se propagó principalmente en la dirección vertical y parcialmente en la dirección lateral.
Gráfico del Eje X:
El punto cercano a -1 millón de amplitud indica una vibración importante en el eje longitudinal, posiblemente originada por el desplazamiento del peso durante el salto.
Esta respuesta podría sugerir cierta resonancia o flexión del sistema en el eje X.
Conclusiones y Recomendaciones:
Filtrado y Análisis Espectral: Aplicar técnicas de filtrado temporal para aislar los eventos de salto de las vibraciones normales operativas permitirá obtener datos más útiles para el mantenimiento del sistema.
Aislamiento del Sistema: Evaluar la implementación de plataformas antivibración que desacoplen las fuentes externas de perturbación del sistema principal.
Sensibilidad del Sistema: Considerar la calibración de los sensores para reducir la captación excesiva de vibraciones externas, enfocándose solo en las vibraciones relevantes para el proceso.

<img width="496" alt="image" src="https://github.com/user-attachments/assets/39fef8c4-4fc4-4f10-8419-bc6d68e992eb" />

A continuación, se analizan los datos obtenidos en el analisis de vibraciones de las escaleras automaticas de elgoibar.Viendo el impacto que genera en los distintos ejes X,Z e Y el salto de personas situadas encima de las escaleras.
Gráfico del Eje Z:
El valor cercano a 100 millones podría estar relacionado con un evento puntual generado por el impacto de una persona o salto brusco.
Dicha magnitud sugiere que el eje vertical es muy sensible a fuerzas externas. Esta sensibilidad puede ser un factor a evaluar para sistemas que requieran estabilidad en el eje Z.
Para reducir estos picos, sería recomendable mejorar el aislamiento de la máquina respecto al entorno.
Gráfico del Eje Y:
La amplitud negativa cercana a -400 mil podría también ser consecuencia de un salto, pero con una menor intensidad en comparación con el eje Z.
El eje Y tiende a captar vibraciones horizontales, lo que sugiere que el impacto del salto se propagó principalmente en la dirección vertical y parcialmente en la dirección lateral.
Gráfico del Eje X:
El punto cercano a -1 millón de amplitud indica una vibración importante en el eje longitudinal, posiblemente originada por el desplazamiento del peso durante el salto.
Esta respuesta podría sugerir cierta resonancia o flexión del sistema en el eje X.
Conclusiones y Recomendaciones:
Filtrado y Análisis Espectral: Aplicar técnicas de filtrado temporal para aislar los eventos de salto de las vibraciones normales operativas permitirá obtener datos más útiles para el mantenimiento del sistema.
Aislamiento del Sistema: Evaluar la implementación de plataformas antivibración que desacoplen las fuentes externas de perturbación del sistema principal.
Sensibilidad del Sistema: Considerar la calibración de los sensores para reducir la captación excesiva de vibraciones externas, enfocándose solo en las vibraciones relevantes para el proceso.

- Otro tipo de visualización https://public.tableau.com/app/profile/david.joel.rodriguez.saravia/viz/Ascensores_prueba/Hoja1?publish=yes

- Aquí se muestra las imágenes de las ubicación de los 3 ascensores de Ermua 

- Análisis de Ascensor Tiempo de anomalias/elevador/recuento de personas:

- Aquí se muestra una gráfica de los ascensores de Ermua donde se muestra la relación entre el tiempo de anomalías el elevador y el recuento de personas

- https://public.tableau.com/app/profile/david.joel.rodriguez.saravia/viz/AnlisisAscensoresErmuaTiempo_de_anomalias_elevador_recuento_de_personas/Hoja1?publish=yes

![Escalera - Prueba 1](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%201.png)

![Escalera - Prueba 2](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%202.png)

![Escalera - Prueba 3](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%203.png)

![Escalera - Prueba 4](Datos%20vibraci%C3%B3n/Imagenes%20de%20resultados/Escalera%20-%20Prueba%204.png)

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

Realidad Aumentada 
https://aventurero7.github.io/Realidad-Aumentada/index.html





