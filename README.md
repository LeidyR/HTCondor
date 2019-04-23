# HTCondor
En este repositorio se mostrará como se puede ejecutar una tarea en HTcondor.

Para llevar a cabo esta demostración se toma como ejemplo el planteado de la diapositiva numero 41 de la siguiente presentación:

https://docs.google.com/presentation/d/1_D_Q6aC9fJk1QEOeaOfEPR51IPQw-fd1VEmcZyL0mnE/edit#slide=id.p4

# Ejecución

Descargar el archivo R.tar.gz y añadirlo al directorio, dentro en la carpeta Ex02_R una vez descargado y descomprimido el contenido de este repositorio:

https://drive.google.com/file/d/1gv9hnrQCN0K517RzRWXFdcgL0tzqh9h7/view

Una vez descargados los archivos se ejecutarán los siguientes pasos.

Levantar el contenedor:

docker run -d --rm --mount type=bind,source=/home/leidy/Escritorio/HTCondor-master/WorkshopComputationalPlatforms-master/HTCondor_2017/Ex02_R,target=/home/submitter -w /home/submitter -h htcondor --name htcondor andypohl/htcondor

IMPORTANTE: En la opción "source" va la ruta especifica de donde se encunetran sus archivos descargados.

Acceder a  él:

docker exec -it -u 1000:1000 htcondor bash

Una vez se ingrese procedemos a ejecutar la tarea:

condor_submit testR.condor
