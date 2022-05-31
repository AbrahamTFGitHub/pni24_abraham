# EJERCICIO-1

<center>

![](/img/ejercicio1.png)

</center>

1. Cambia el nombre del switch a **S1**.

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~


2. Creamos las VLAN y le asignamos un nombre a cada siguiendo el criterio:

+ vlan 10 -> **proyecto10**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

+ vlan 20 -> **proyecto20**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

+ vlan 30 -> **proyecto30**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

3. Asignamos las máquinas a cada una de las vlan creadas siguiendo el criterio siguiente:

+ PC1, PC5 y PC8 forman el equipo de trabajo para el desarrollo del **proyecto10**

####PC1
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

####PC5
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

####PC8
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~
+ PC2 y PC6 forman el grupo de trabajo para el desarrollo del **proyecto20**

####PC2
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

####PC6
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~
+ PC3, PC4 y PC7 forman el grupo de trabajo para el desarrollo del **proyecto30**

####PC3
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

####PC4
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

####PC7
~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~
4. Mostramos un resumen de las redes vlan creadas:

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

5.Guardamos la configuración del switch

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

6. Configuramos las direcciones `ip`de cada uno de los equipos siguiendo el siguiente criterio:

+ Vlan 10 -> proyecto10 -> 10.0.10.0/24
+ Vlan 20 -> proyecto20 -> 10.0.20.0/24
+ Vlan 30 -> proyecto30 -> 10.0.30.0/24

Una vez hecho esto comprobar que sólo hay comunicación entre los distintos equipos que forman parte de la misma red vlan.



# EJERCICIO-2

Partiendo del ejercicio de un switch ya resuelto, añadir un switch S2 conectado a S1. Este switch tendrá:

+ En el puerto 9 el equipo PC9 del **proyecto10**.
+ En el puerto 10 el equipo PC10 del **proyecto20**.
+ En el puerto 11 el equipo PC11 del **proyecto30**.
+ El troncal estará en el primer puerto gigabitethernet de los dos switches

>***NOTA-1***: Conectamos los equipos al switch y les asignamos a cada uno de ellos las `ip`correspondientes **PERO NO CONFIGURAMOS NINGUNA VLAN EN EL SEGUNDO SWTICH**, ya que vamos a hacer uso del protocolo **VTP** para que el primer switch se comporte como **servidor** y el segundo como **cliente**

>***NOTA-2***: no conectar los dos switches entre sí hasta no configurar el **VTP**


<center>

![](/img/ejercicio2.png)

</center>


1. Configura el switch S1 como **servidor** dentro del protocolo **VTP**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

2. Muestra el estado del protocolo **VTP** en el switch S1

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

3. Conficura el puerto `Gig0/1` en modo **troncal**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

4. Configura el switch S como **cliente** dentro del protocolo **VTP**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

5. Muestra el estado del protocolo **VTP** en el switch S2

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~


6. Configura el puerto `Gig0/1`del switch S2 en modo **troncal**

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

7. Muestra un resumen de las redes vlan del switch S2 (no debe haber ninguna vlan salvo la que se crea por defecto)

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

8.Conecta los puertos `Gig0/1` de ambos switches.

9. Muestra un resumen de las redes vlan del switch S2. ¿Qué diferencia hay ?

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~


~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~




# EJERCICIO-3

<center>

![](/img/ejercicio3.png)

</center>

Conectar un **router 1841** al switch 2 por el puerto `Fa0/1` del router.

1. Configuramos  el router para hacer enrutamiento entre VLANs (Router On A Stick). Para ello creamos sub-interfaces para cada vlan en el puerto `Fa0/1` del router:

+ Sub-interfaz para la vlan 10

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

+ Sub-interfaz para la vlan 20

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

+ Sub-interfaz para la vlan 30

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

2. Configuramos la interfaz `Fa0/0` con un servidor para hacer pruebas de conectividad. Utiliza las `ips` de la red `192.168.1.0/2` para esta nueva red.

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

3. Muestra la tabla de enrutamiento del router.

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~

4. Guarda la configuración del router.

~~~
PEGA EL TEXTO DEL TERMINAL AQUÍ
~~~
