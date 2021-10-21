1. Defina los tres modos de transmisión:
- Simplex: Es de modo unidireccional, solo uno de las dos estaciones puede transmitir, la otra solo recibe.
- Semiduplex: Es de cada estación puede tanto enviar como recibir, pero no simultaneamente, la capacidad total del canal se usa mediante los dos dispositivos que esta transmitiendo.
- Full-duplex: Es donde ambos pueden enviar y recibir al simultáneamente, las señales que van en ambas direcciones comparten la capacidad del enlace.
2. Indique las ventajas de cada tipo de topología de red.
 
  - Malla:
     El uso de los enlaces dedicados garantiza que cada conexión solo debe transportar la carga de datos propia de los dispositivos conectados.
     La topología en malla es robusta o sea si un enlace falla no activa todo el sistema.
     Privacidad o seguridad, cuando el mensaje viaja a través por la línea, solamente le llega al receptor. Los muros evitan que otros usuarios puedan tener acceso a los mensajes.
     El enlace punto a punto hace que se pueda identificar y salir los errores mas recientes.
    
    
   - Estrella:
      Es mucho mas barata que una topología en malla.
      Cada dispositivo necesita solamente un enlace y un puerto de entrada/salida.
      Fácil de instalar y reconfigurar.
      Si falla algun enlace, solamente se veria afectado, todos los demás enlaces estan activos. Permite identificar y quitar fallos de una forma muy sencilla.
  
  
  - Árbol:
      Tiene las mismas ventajas de estrella.
      Permite que se conecten más dispositivos a un único concentrador.
      Permite a la red aislar y dar prioridad las comunicaciones de distintos ordenadores.
   
   
   - Bus:
     Instalación facil.
     Usa menos cables que las de tipo malla, estrella y árbol.
  
  
  - Anillo:
     Fácil de instalar y reconfigurar.
     Los fallos se aíslan de forma sencilla, por medio de alarma.
 
 
   - Topologías hibridas:
     Conectar cualquier tipo de topología con otra.

3. ¿Cuáles son los factores que determinan que un sistema de comunicación sea una LAN, MAN o WAN?

- LAN: Red de propiedad privada que conecta enlaces de una único edificio o campus.
- MAN: Red que se puede extender a lo largo de la ciudad.
- WAN: Red que puede extenderse a través de regiones, países o por todo el mundo.

4.Enumere las cinco topologías básicas de red: Malla, Estrella, Árbol, Bus, Anillo.

5.Indique una desventaja de cada tipo de topología de red.

 - Malla: Numero de puertos de entrada/salida necesarios.

  - Estrella y Árbol: Cantidad de cable

  - Bus: Un fallo o ruptura del cable de bus interrumpe todas las transmisiones.

  - Anillo: El tráfico unidireccional es una desventaja, ya que una ruptura puede inhabilitar toda la red.

6. Para una red con n dispositivos, ¿cuál es el número de enlaces de cable necesarios para una malla, un anillo, un bus y una topología en estrella?
- malla: n(n-1)/2.
- anillo: nº dispositivos = nº cables de enlace.
- bus: nº dispositivos = n+1 enlace.
- estrella: En el concentrador tienen que ir numero de puertos por numero de dispositivos.


7. Para cada tipo de topología de red, indique las implicaciones de que exista un fallo de un único cable.
- Malla: Si algún enlace falla inhabilita todo el sistema.
- Estrella: Si un enlace falla solo este se ve afectado.
- Árbol: Lo mismo que el de estrella.
- Bus: Un fallo o rotura de cable interrumpe todas las transmisiones.- 
- Anillo: Una rotura del anillo puede inhabilitar toda la red.
8.  ¿Qué es una internet? ¿Qué es Internet?
Una internet es una serie de redes interconectadas.
Internet: es la red de ámbito mundial.
9. ¿Qué topología necesita controlador central o un concentrador? Estrella
10. La comunicación entre una computadora y un teclado implica una transmisión simplex.
11. En una red con 25 computadoras, ¿qué topología necesitaría el cableado más extenso? Malla.
12. Una topología en árbol es una variación de una topología en estrella.
13. Una conexión punto a punto proporciona un enlace dedicado entre dos dispositivos.
14. En la transmisión full-duplex, la capacidad del canal es siempre compartida por los dos dispositivos que se comunican.
15. Una rotura de cable en una topología en bus detiene toda la transmisión.
16. Una red que contiene múltiples concentradores esta configurada muy probablemente como una topología en árbol.
17. Defina el tipo de topología de las siguientes figuras:
![image](https://user-images.githubusercontent.com/90834831/138235872-453f2277-8229-47db-a478-a5610f7612d7.png)
18. Relacione los conceptos siguientes con una topología de red (cada uno se puede aplicar a más de una topología):

       a) Se pueden añadir nuevos dispositivos fácilmente: Bus.
       
       b) El control se efectúa a través de un nodo central: Estrella.
       
       c) El tiempo de transmisión se gasta reenviando los datos a través de nodos intermedios: Árbol.

      
19.Cuando alguien hace una llamada telefónica local a otra persona, ¿está usando una configuración de línea punto a punto o multipunto? Explique su respuesta:


Si la llamada es local a otro punto de la ciudad es punto a punto, pero si dentro de oficina edificio, etc.. es multipunto.

20. ¿Qué modo de transmisión (símplex, semidúplex o full-dúplex) se puede comparar a los siguientes?

     a) Una conexión computadora a monitor: Simplex.
     
     b) Una conversación educada entre tía Gertrudis y tía Rowena: Full-duplex. 
     
     c) Una emisión por televisión: Simplex.
     
