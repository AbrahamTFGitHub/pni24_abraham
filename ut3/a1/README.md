1.¿Qué niveles OSI son los niveles de soporte de red? Los niveles físicos de enlace de datos y de red.

2.¿Qué niveles OSI son los niveles de soporte de usuario? Los niveles de Sesión, Presentación y Aplicación.

3.¿Cómo están OSI e ISO relacionadas entre sí?  ISO es la organización que creo del modelo OSI.

4.Enumere los niveles del modelo OSI: 7.Aplicación 6.Presentación 5.Sesión 4.Transporte 3.Red 2.Enlace de datos 1.Física.

5.¿Cómo pasa la información de un nivel OSI al siguiente? 
Cada capa del protocolo pasa datos a la capa siguiente, le añade datos propios de control y despues pasa al resto a la siguiente capa.

6.¿Qué son las cabeceras y cola y cómo se añaden y se quitan? Son los datos de control añadidos al comienzo o final del paquete de datos, las cabeceras se unen al paquete en los niveles de Presentación, Sesión, Transporte, Red, Datos y en este el de Datos añade una cola.

7.¿Cuáles son las responsabilidades del nivel físico? 
Coordina las funciones necesarias para transmitir un flujo de bits sobre un medio físico.

8.¿Cuáles son las responsabilidades del nivel de enlace? 
Se encarga de la entrega de unidades de datos de una estación a la siguiente sin errores.

9.¿Cuáles son las responsabilidades del nivel de red? 
Se encarga de la entrega de paquetes del origen al destino mediante múltiples enlaces de red.

10.¿Cuáles son las responsabilidades del nivel de transporte? 
Es el responsable de la entrega de origen a destino de todo el mensaje.


11.El nivel de transporte crea una conexión entre el origen y el destino. ¿Cuáles son los tres eventos involucrados en la conexión? 
- Establecimiento de la conexión
- Transferencia de datos
- Liberación de la conexión

12.¿Cuál es la diferencia entre una dirección de punto en servicio, una dirección lógica y una dirección fisica? 
- Punto de servicio: La cabecera del nivel de transporte debe además incluir un tipo de dirección denominado dirección de punto de servicio o dirección de puerto.
- Lógico: El nivel de red añade una cabecera al paquete que viene del nivel superior que, incluye las direcciones lógicas del emisor y el receptor.
- Físico: El nivel de enlace de datos añade una cabecera a la trama para definir la dirección física del emisor(origen) y/o receptor(destino) de la trama.

13.¿Cuáles son las responsabilidades del nivel de sesión? 
- Control de dialogo: Permite que dos sistemas tengan un dialogo.
- Sincronización: Permite que un proceso pueda añadir checkpoints en un flujo de datos.

14.¿Cuáles son las responsabilidades del nivel de presentación? 
Asegura la interoperabilidad entre distintos dispositivos de comunicación mediante la transformación de datos a un formato común.

15.¿Cuál es el objetivo de la traducción en el nivel de presentación? 
Los procesos o programas en ejecución en los sistemas intercambian información en caracteres, números, etc. Hay que traducir la información a un flujo de bits antes de transmitirla. El nivel de presentación en el emisor cambia la información del formato dependiendo del emisor a un formato común.

16.Indique alguno de los servicios proporcionados por el nivel de aplicación. 
- Terminal virtual de red: Es un de un terminal físico y permite al usuario acceder a una maquina remota. Por ejemplo, la aplicación crea un software de un terminal emulado en la maquina remota.
- Servicio de correo: Esta aplicación proporciona las bases para el envió y almacenamiento del correo electrónico.

17.¿Cómo se relacionan los niveles de la familia del protocolo TCP/IP con los niveles del modelo OSI?
El TCP/IP tiene cinco niveles: Físico, Enlace, Red, Transporte y Aplicación. Los primeros cuatro niveles proporcionan estándares físicos, interfaces en red, conexión entre redes y funciones de transporte que corresponden con los cuatro primeros niveles de OSI. Pero, los tres modelos superiores de  OSI están en TCP/IP mediante un único nivel de aplicación.

18. El nivel sesión decide la localización de los puntos de sincronización. 
19. En el nivel enlace de datos, la unidad de datos se denomina trama.
20. Los servicios de correo y de directorio están disponibles a los usuarios de la red a través del nivel: aplicación.
21. A medida que los paquetes de datos se mueven  de los niveles inferiores a los superiores las cabeceras: añadidas.
