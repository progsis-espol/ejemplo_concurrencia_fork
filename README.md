# Ejemplo uso de sockets y fork() para concurrencia de conexiones
Ejemplo sobre uso básico de sockets en Linux usando C para la materia Programación de Sistemas (CCPG1008) de la ESPOL.

## Instrucciones
Esta aplicación cliente - servidor admite la conexión simultanea de varios cliente mediante la creación de un proceso hijo por cliente usando *fork()* en el servidor. La aplicación es un *eco* cliente - servidor. Es decir, el usuario ingresa una línea de texto desde el cliente, el cliente la envia al servidor y el servidor la envia de regreso.

El programa servidor *server* tiene el siguiente comportamiento:
```
$ ./server -h
Servidor ejemplo apliación eco.
uso:
 ./server <puerto>
 ./server -h
Opciones:
 -h			Ayuda, muestra este mensaje
```

El programa cliente *client* tiene el siguiente comportamiento:
```
$ ./client -h
Cliente ejemplo aplicación eco.
uso:
 ./client <hostname> <puerto>
 ./client -h
Opciones:
 -h			Ayuda, muestra este mensaje
```
Asumiendo que el servidor esta corriendo en una maquina con la IP 192.168.100 en el puerto 8080 y que tiene un archivo *prueba.txt* con 65 bytes de tamaño. Ejemplo de ejecución del cliente:
```
$ ./client 192.168.100 8080
Conectado exitosamente a 192.168.100 en el puerto 8080.
Ingrese el nombre del archivo a descargar: prueba.txt
Descargando y grabando en disco prueba.txt (65 bytes)...
Ingrese el nombre del archivo a descargar:
```
## Compilación
Para compilar cliente y servidor:
```
$ make
```
Para compilar solo el servidor:
```
$ make server
```
Para compilar cliente y servidor facilitando la depuración con gdb:
```
$ make debug
```
Para compilar cliente y servidor habilitando la herramienta AddressSanitizer, facilita la depuración en tiempo de ejecución:
```
$ make sanitize
```
