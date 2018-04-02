# Primer Examen parcial de Sistemas Operativos 

**Nombre:** Cristian Alejandro Morales Lopez

**Codigo** A00328064

 Todo esta almacenada en la Rama cam/so-exam1 ([URL del fork desde camtelematica](https://github.com/camtelematica/so-exam1.git))

### **Validacion de la imagen ISO de Debian 9**

Una vez obtenida la imagen ISO ([URL de la ISO del Sistema Operativo Debian 9](https://www.debian.org/distrib/netinst)) se procede con los siguientes pasos:
- se procede a descargar el software md5 este es el encargado de la comprabacion de que el checksum de la imagen ISO descargado no halla sufrido ningun error durante este proceso.
- instalar el programa y ejecutarlo
- desde el software se seleciona la ruta del almacenamiento del archivo y se genera el codigo de comprobacion de checksum y se compara con el checksum brindado por la pagina de debian [URL comprobacion checksum de Debian 9](http://cdimage.debian.org/debian-cd/current/amd64/iso-cd/MD5SUMS) si todo esta correcto deben de tener el mismo numero de verificacion como se aprecia en la imagen 

![](/A00328064/capturas/Md5.PNG)

### **Pasos para la instalacion del sistema operativo debian 9**

para el montaje del sistema operativo se realizo sobre el software **Oracle Virtual Box**

se ejecuta el programa anteriormente mencionado y se crea una nueva maquina virtual y se Ejecutan los siguientes para su montaje: 

0. asignar nombre a la maquina virtual 
1. tipo (linux)
2. elegir la version (Debian 64-bit)
3. asignar tamaño de memoria RAM 3GB
4. Asignar Disco duro (crearun disco duro virtual ahora) 
5. tipo de archivo de virtualizacion VDI (Virtual Disk Image)
6. Almacenamiento en unidad de disco duro fisica (reservado dinamicamente)
7. Ubicacion del archivo y tamaño 10 GB

**EN OPCIONES SE CONFIGURAN LAS SIGUIENTES OPCIONES**

8. configurar orden de arranque escojer optica
9. configurar en red una interfaz puente
10. almacenamiento en atributos escoger la ubicacion con la imagen iso del sistema operativo
11. seleccion del modo de instalacion grafica


**UNA VEZ CONFIGURADA LA MAQUINA VIRTUAL EN ORACLE VIRTUAL BOX SE PROCEDE A LA CONFIGURACION DEL SISTEMA OPERATIVO DEBIAN 9**

12. seleccion del idioma Spanish
13. selecionar la ubicacion
14. seleccion del estilo del teclado
15. creacion del usuario root y usuario invitado
16. instalacion de debian en el disco 
17. configuracion del gestor de paquetes colombia 
18. configurar el gestor de paquetes debian.uniminuto.edu
19. selector de scripts
20. instalador grbu
21. ejecutar el instalador de paquetes 
22. reiniciar el sistema operativo 

**UNA VEZ INSTALADO EL SISTEMA OPERATIVO PARA OBTENER LA INFORMACION DEL SISTEMA OPERATIVO SE PROSIGUE DE LA SIGUIENTE MANERA**

23. se logea con el usuario anteriomente creado
24. se abre una terminal nueva
25. se ejecuta el siguiente comando para obtener informacion del sistema operativo **lsb_release -a** a lo cual se obtiene la siguiente informacion 

![](/A00328064/capturas/versionn%20del%20software.PNG)

**FINALMENTE TENEMOS NUESTRA MAQUINA VIRTUAL INSTALADA Y CONFIGURADA CORRECTAMENTE**

### **Conexion SSH a la Maquina Virtual**

- para la conexion SSH a la maquina virtual anteriormente se configuro la interfaz puente en la instalacion de la maquina virtual la cual se realiza ingresando a opciones despues a redes y despues se seleciona la interfaz-

![](/A00328064/capturas/adaptador%20puente.PNG)


- cuando configure la instalacion de Debian 9 en el instalador de paquetes instale el paquete de conexion SSH lo cual me ayudo dado que no tuve problemas a la hora de la conexion. Se Realiza la conexion con el programa **Putty** ingresando la direccion ip que tiene asignada la maquina virtual se procede con la conexion SSH.

![](/A00328064/capturas/putty.PNG)



![](/A00328064/capturas/conexion%20putty.PNG)

### **Instalacion de git y tig**

para la instalacion de git en debian se utilizo el comando en modo sudo $ apt-get install git

![](/A00328064/capturas/install%20git-hub.PNG)

para la instalacion de tig se clono el repositorio  https://github.com/jonas/tig.git en el directorio tmp y se ejecuto el siguiente comando para su instalacion en modo super usuario apt-get install libncurses5-dev libncursesw5-dev

![](/A00328064/capturas/tig.PNG)

![](/A00328064/capturas/tig%202.PNG)


### **Exportacion de la maquina virtual hacia otro PC**

- para la exportacion de la maquina virtual se efectua la opcion de **Oracle Virtual Box** archivo/exportacion de servicio virtual 

![Archivo/exportar servicio virtual](/A00328064/capturas/exportacion.PNG)

- seleccion de maquina virtual 
![](/A00328064/capturas/selecion-maquina.PNG)

- seleccion de ruta de almacenamiento de la maquina virtual donde sera exportada

![](/A00328064/capturas/seleccion-ruta.PNG)

- se exporta la maquina

![](/A00328064/capturas/exportar.PNG)

**IMPORTACION DE LA MAQUINA VIRTUAL**

- Archivo importar servicio virutal

- seleccion de la ruta donde se tiene almacenada la maquina virtual

![](/A00328064/capturas/selecion-importacion.PNG)


![](/A00328064/capturas/selecion-imagen.PNG)

- configurar alguna opcion solo es necesario y finalmente importar

![](/A00328064/capturas/configuracion-final-e-importar.PNG)

## CENTOS7 VS DEBIAN 9

## Debian 9
- Tiene mucho más paquetes en su defecto los repositorios de centos

- Instalación predeterminada es más mínima. Podría ser más fácil en los recursos del servidor y de seguridad.

- Por facilidad de mantenimiento (el apt-get es el mejor amigo de Debian, y Debian no sería Debian sin el apt-get).

- Menor consumo de disco duro (al no instalar paquetes que no usaremos jamás, se ahorra bastante espacio).

- Más control sobre lo que se configura (no dependemos de un script que mañana puede cambiar de nombre o de funcionamiento o que no funcione como esperaba)

- Por tener paquetes más antiguos pero mucho más estables (más testeados y cuyas actualizaciones se basan en la misma versión estable)

- Porque no instala un entorno gráfico por defecto (¿para qué queremos un sistema gráfico en un servidor que no va a tener monitor? ¿Para consumir RAM y procesador?)

- Para disponer de mucha más documentación (Debian es una de las distribuciones más utilizadas actualmente, y más en servidores)
- y porque el “modo texto” no es tan difícil como parece en un principio.

- Como el número de procesos que utiliza Debian de base cabe en una pantalla sin scroll, el consumo de recursos se reduce hasta un 70% 

- Yum es lento con avaricia (un “yum install mc” tarda MÁS incluso que un “apt-get upgrade && apt-get install mc” -que es al fin y al cabo lo que hace-)

## CentOS7
- Tiene más maduro agrupación/virtualización/sistema de archivos de clúster de paquetes fuera de la caja, Utiliza SELinux por defecto 
- Tiene  "enterprise" de estado.
- Kickstart hace la clonación de servidores más fácil. 
- En ocasiones tiene una mejor documentación.


- El que tiene menos paquetes disponibles en su defecto en comparación con los repositorios de debian, incluso después de la habilitación de EPEL.

- Centos no se cuelga Efectivamente, una de las principales características y ventajas de Centos es que su sistema operativo es muy estable, evitando así los cuelgues que dejan el sistema completamente bloqueado.



- Rapidez Si hay una cosa cierta y una ventaja contundente que va ligada a Centos es la velocidad a la que trabaja este sistema operativo, mucho más superior que cualquiera de los otros sistemas basados en linux, sin excepciones ni competidores reales.
El hecho de que Centos sea tan rápido se debe, fundamentalmente, a que solo se dedica a ejecutar las versiones más básicas y estables del software y, de este modo, el procesador no tiene que lidiar con un sinfín de aplicaciones distintas y abiertas al mismo tiempo.

- Centos Server Asimismo, los programas de este sistema operativo son menos susceptibles de tener gusanos que bloqueen o que ataquen a la seguridad. De tenerlos, la velocidad se vería muy afectada por ralentizaciones y cuelgues, algo que no es muy poco probable, por no decir que es prácticamente imposible, con Centos.

- Pocas actualizaciones adicionales A través de Centos se opera con un sistema bastante confiable, que precisa de muy pocas actualizaciones y que las hace a la vez que su "hermano" comercial Red Hat Enterprise Server. Al mismo tiempo, se debe destacar que su soporte de actualización es de un lustro.



Fuentes:
- https://www.enmimaquinafunciona.com/pregunta/96542/diferencias-entre-debian-y-centos-desde-un-servidor-web-prospectiva
- https://webtematica.com/centos-o-debian-para-servidores-web
- https://www.sinologic.net/2011-02/porque-debian-no-centos.html



