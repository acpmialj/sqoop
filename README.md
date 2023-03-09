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

Ejecutamos Jupyter Notebook desde dentro del contenedor con "jupyter notebook". Nos dará un enlace
de conexión Jupyter. Creamos un Notebook Python nuevo. Y listo para probar el movimiento de datos
MariaDB <-> HDFS
