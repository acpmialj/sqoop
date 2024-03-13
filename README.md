# sqoop

Lanzamos contenedor con Hadoop, MariaDB, Sqoop y Jupyter.

```
docker run --rm -it \
    --name sqoop \
    -p 50070:50070 \
    -p 8088:8088 \
    -p 8888:8888 \
    -v "$PWD":/workspace \
    jdvelasq/sqoop:1.4.7
```
Si todo va bien, en pantalla veremos:
```
---------------------< stack >---------------------
apache/ubuntu  20.04
jupyterlab  3.2.9         
hadoop  2.10.1        
mariadb  10.3.34          
sqoop  1.4.7 
---------------------------------------------------  
Hadoop NameNode at:     http://127.0.0.1:50070/  
Yarn ResourceManager at:      http://127.0.0.1:8088/ 
--------------------------------------------------- 
```
Además, estaremos en un shell del contenedor. 

Ejecutamos Jupyter Lab desde dentro del contenedor (jupyter-lab). Nos dará unos enlaces para lanzar el navegador web, usamos el último (http://127.0.0.1:8888...). 

Ya en la interfaz web de jupyter-lab, podemos crear un notebook Python nuevo y replicar los pasos indicados en "sqoop.ipynb", para probar el movimiento de datos MariaDB <-> HDFS. También podemos descargar desde este repositorio Github el cuaderno indicado, y subirlo a jupyter para su ejecución.

Nótese que el cuaderno lo gestiona el servidor Jupyter que se ejecuta en el conteenedor. Lo almacena en el directorio /workspace -- que está mapeado al directorio del host desde el cual se lanzó el contenedor. Por lo tanto, el cuaderno queda accesible tras eliminar el contenedor. También podemos tener una copia con el notebook abierto, usando la opción File -> Download del menú principal de Jupyter. 
