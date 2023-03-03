 NOTA: Comence este esquema. Las ideas son bienvenidas y las dudas seran aclaradas. 
      Este proyecto puede prometer si se hace bien, con calma pues no disponemos de
     todo el tiempo del dia para ello pero si hay fe de que se puede lograr en poco tiempo
      Principal objetivo:
        -> Aprender a trabajar en equipo. (Git y GIthub).
        -> Aprender de todo.

 >>Proyecto: Performance Monitoring (El nombre va a cambiar)


 >Objetivos iniciales:

 Realizar una herramienta que permita visualizar el estado de parametros de gran importancia para el buen 
 funcionamiento de Radiobases celulares de ETECSA. Los parametros a visualizar serian algunos que
 los softwares de gestion existentes no muestren. La idea no es mostrar lo que falte por mostrar en estos sistemas
 que ya brindan informacion, sino que nuestra herramienta consulte regularmente ciertos parametros en las 
 bases de datos de los equipos y sean alamcenados en nuestra base de datos. 
 Posteriormente, con el conjnto de datos que se tendra por cada equipo se realiza una lista para poder 
 mostrar un historico de los valores en el tiempo para chequear el desempeno de estos parametros en cada
 uno de los  equipos,(mejora, se mantiene o si empeora). 
 Como resultado se podria anticipar y preveer interrupciones o roturas, y hasta en el mejor de los casos
 predecir comportamientos de trafico y optimizacion de la red. 
 
 
 >Antecedentes:
 Existe una base de datos que contiene los parametros y valores de cada radiobase en tiempo real pero la
 forma de realizar consultas es muy robusta y arcaica.
 Se realizo una herramienta web que con los valores de esa base de datos realiza ploteos y muestra el pomportamiento
 de las radiobases y brinda mucha informacion la cual es revisada practicamente a diario para conocer el 
 estado de la red y asi se notan los problemas existentes en la red. 
 Ademas que los supervisores chequean en "tiempo real e ininterrumpida" el panel donde muestra las 
 alarmas de la red, las cuales muestran cuando los equipos se rompen o tienen problemas.
 
 Estas dos herramientas son muy utiles pero aun no logran ayudarnos a predecir las interrupciones ya que 
 ellas te avisan cuando ya se rompio y no cuando se va degradando el servicio poco a poco. Hay roturas 
 que no hay formas de predecirlas o anticiparse, por ejemplo:
 - Roturas de los radios por truenos, apagones inesperados, etc que se rompen al momento.
 - Interrupcion de la transmision (Ratones que se comen los cables, etc)
 - Entre otros
 
 Pero existen otros que si pueden ser observados y evaluar su comportamiento y tomar acciones antes de que 
 se acaben de romper:
 - Atenuacion en los conectores (humedad, agua dentro, golpes, mal montaje, falta de taipe)
     -> Este se ve por un parametro que se llama ROE (Es el nivel de atenuacion o perdidas que existe en
      el able) 
 
 - Atenuacion en el enlace de transmision (SFP: Conectores de fibra optica)
     -> Valor de Potencia de Transmision y recepcion Optica en el SFP.
 - Otros
 
 
 >Entonces:
 
 En una primera version nos concentraremos en simplemente mostrar los valores de ROE (O VSWR, es lo mismo) 
 pues en un casi 100% de los casos que existe problemas en una radiobase este valor se revisa debido a que 
 las herramientas que ya existen (WEB de metricas y el panel de alarmas) no muestran estos valores porque 
 son valores fisicos y solo se obtienen accediendo individualmente a cada radiobase a traves del sistema 
 de gestion remoto o local. Por tanto, este valor de VSWR a fin de cuentas muestra el desempeno de la 
 radiobase y nosotros lo extraeriamos periodicamente de la base de datos de cada una para poder realizar 
 el historico y ver su comportamiento.
 
 
 >Objetivos especificos:
 - Realizar las consultas periodicas de la base de datos de las radiobases.
 - Disenar y organizar la informacion extraida en nuestra nueva base de datos.
 - Crear las aplicaciones (WEB, Desktop y/o Mobile) para mostrar la informacion.
 
 
 *********************************************************************************************************
 ******************************         Fin del aporte metodologico         ******************************
 *********************************************************************************************************
 
 Etapa 1 (Adquisicion de datos):
 
 muestra --> cada consulta del valor de VSWR a las radiobases. Todas las muestras del valor de la VSWR de 
            la base de datos van dentro de 1 reporte.
reporte --> cada archivo a procesar para insertarlo en nuestra base de datos
 
 - Ver como se extraen los valores y en que formato (EXCEL, CSV, otros)
     -> En que frecuencia se hara.
     -> Cantidad de muestras
     -> Cantidad de muestras por cada reporte.
 - Ver el formato que tendra los reportes
 
 
 
 Etapa 2 (Acondicionamiento de la informacion): 
 
 Realizar el proceso de parsear la informacion para convertirla en un formato que sea organizado para su 
 posterior insercion en la base de datos. 
 
 Etapa 3 (Base de datos):
 
 Conformar la base de datos con todos los valores bien organizados.
 La base de datos por el momento de desarrollo seria Github o cualquier repositorio online que brinde la posibilidad
 de terminar el proyecto.
 
 
 
 Etapa 4 (Aplicaciones Front-End):
 
 Realizar aplicacion para consumir estos valores y lograr los objetivos.
