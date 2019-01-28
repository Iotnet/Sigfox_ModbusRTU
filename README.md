Devkit_Modbus_RTU
=================

-	[Introducción](#introducción)

-	[Material](#material)

Introducción
------------

En este repositorio se mostrará un ejemplo de la implementacion del protocolo de comunicacion Modbus-RTU en el Devkit de NXTIoT con un equipo con comunicacion Modbus-RTU e interfaz RS485.

Modbus es un protocolo de comunicacion industrial para la comunicación entre dispositivos para la automatización, el cual esta basado en el protocolo solicitud-respuesta (request-response) con una relacion Maestro-esclavo entre los diferentes dispositivos.

![devkit2mod](https://github.com/NXTIoT/Devkit_Modbus_RTU/blob/master/imagen/modbus3.png?raw=true)

Basicamente, dentro de la red de dispositivos, existe un dispositivo Maestro (Master) dentro de la red, que se encarga de enviar las solicitudes por medio del bus de comunicacion a los diferentes dispositivos esclavos (slaves) que tienen una direccion unica asignada. De esa manera los dispositivos esclavos reconocen la peticion y emiten una respuesta hacia el Maestro, en caso de que sea necesario.

Modbus RTU define una trama de datos especifica para la comunicación entre los dispositivos dentro del bus de comunicación y esta definida de la siguiente manera:

![devkit2mod](https://github.com/NXTIoT/Devkit_Modbus_RTU/blob/master/imagen/modbus4.png?raw=true)

donde 
<br /> Slave address : es la direccion de esclavo del dispositivo.
<br /> Function Code : es el comando de la funcion.
<br /> Data : datos dependiendo de la función utilizada.
<br /> CRC :  codigo de verificación de error de la trama enviada.

Un ejemplo de trama de datos es el siguiente:

    010300010006

donde 

<br />  0x01  es la direccion de esclavo del dispositivo
<br />  0x03  es el comando para leer registros
<br />  0x0001 es el registro de inicio
<br />  0x0006 es el numero de registros a leer
<br />  0xxxxx es el codigo de verificacion de error (CRC)



para conocer mas sobre este protocolo ir al siguiente link:

http://www.ni.com/white-paper/52134/es/

Material
--------

Para este ejemplo se utilizará:

  - Devkit NXTIoT 
  - Modulo de RS485
  - Dispositivo con interfaz RS485 y protocolo Modbus-RTU

El diagrama de conexion es el siguiente:

![devkit2mod](https://github.com/NXTIoT/Devkit_Modbus_RTU/blob/master/imagen/modbus1.png?raw=true)

Los Pines 2 y 3 son utilizados para la comunicacion serial con el modulo de RS485, y el pin 9 es utilizado para habilitar el modo de transmision o recepcion del modulo dentro del bus de comunicacion.
