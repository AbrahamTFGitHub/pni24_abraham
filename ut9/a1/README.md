# EJERCICIO-1

<center>

![](/img/ejercicio1.png)

</center>

1. Cambia el nombre del switch a **S1**.

~~~
Switch(config)#hostname S1
S1(config)#
~~~


2. Creamos las VLAN y le asignamos un nombre a cada siguiendo el criterio:

+ vlan 10 -> **proyecto10**

~~~
S1(config)#vlan 10
S1(config-vlan)#name proyecto10
~~~

+ vlan 20 -> **proyecto20**

~~~
S1(config-vlan)#vlan 20
S1(config-vlan)#name proyecto20
~~~

+ vlan 30 -> **proyecto30**

~~~
S1(config-vlan)#vlan 30
S1(config-vlan)#name proyecto30
~~~

3. Asignamos las máquinas a cada una de las vlan creadas siguiendo el criterio siguiente:

+ PC1, PC5 y PC8 forman el equipo de trabajo para el desarrollo del **proyecto10**

####PC1
~~~
S1(config)#interface FastEthernet 0/1
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 10
~~~

####PC5
~~~
S1(config)#interface FastEthernet 0/5
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 10
~~~

####PC8
~~~
S1(config)#interface FastEthernet 0/8
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 10
~~~
+ PC2 y PC6 forman el grupo de trabajo para el desarrollo del **proyecto20**

####PC2
~~~
S1(config)#interface FastEthernet 0/2
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 20
~~~

####PC6
~~~
S1(config)#interface FastEthernet 0/6
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 20
~~~
+ PC3, PC4 y PC7 forman el grupo de trabajo para el desarrollo del **proyecto30**

####PC3
~~~
S1(config)#interface range Fa0/3-4
S1(config-if-range)#switchport mode access
S1(config-if-range)#switchport access vlan 30
~~~

####PC4
~~~
S1(config)#interface range Fa0/3-4
S1(config-if-range)#switchport mode access
S1(config-if-range)#switchport access vlan 30
~~~

####PC7
~~~
S1(config)#interface FastEthernet 0/7
S1(config-if)#switchport mode access 
S1(config-if)#switchport access vlan 30
~~~
4. Mostramos un resumen de las redes vlan creadas:

~~~
S1#show vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/9, Fa0/10, Fa0/11, Fa0/12
                                                Fa0/13, Fa0/14, Fa0/15, Fa0/16
                                                Fa0/17, Fa0/18, Fa0/19, Fa0/20
                                                Fa0/21, Fa0/22, Fa0/23, Fa0/24
                                                Gig0/1, Gig0/2
10   proyecto10                       active    Fa0/1, Fa0/5, Fa0/8
20   proyecto20                       active    Fa0/2, Fa0/6
30   proyecto30                       active    Fa0/3, Fa0/4, Fa0/7
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    
~~~

5.Guardamos la configuración del switch

~~~
S1#copy running-config startup-config 
Destination filename [startup-config]? 
Building configuration...
[OK]
S1#
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
S1#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
S1(config)#vtp d
S1(config)#vtp domain vlan
Changing VTP domain name from NULL to vlan
S1(config)#vtp mode 
S1(config)#vtp mode s
S1(config)#vtp mode server 
Device mode already VTP SERVER.
S1(config)#vtp password 1234
Setting device VLAN database password to 1234
S1(config)#vtp version 2
S1(config)#%SPANTREE-2-RECV_PVID_ERR: Received 802.1Q BPDU on non trunk FastEthernet0/24 VLAN1.
%SPANTREE-2-BLOCK_PVID_LOCAL: Blocking FastEthernet0/24 on VLAN0001. Inconsistent port type.
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/24, changed state to down
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/24, changed state to up
~~~

2. Muestra el estado del protocolo **VTP** en el switch S1

~~~
S1#show vtp status
VTP Version capable             : 1 to 2
VTP version running             : 2
VTP Domain Name                 : vlan
VTP Pruning Mode                : Disabled
VTP Traps Generation            : Disabled
Device ID                       : 0030.F28B.1800
Configuration last modified by 0.0.0.0 at 3-1-93 00:04:22
Local updater ID is 0.0.0.0 (no valid interface found)

Feature VLAN : 
--------------
VTP Operating Mode                : Server
Maximum VLANs supported locally   : 255
Number of existing VLANs          : 8
Configuration Revision            : 1
MD5 digest                        : 0xBB 0x52 0x2E 0x29 0x84 0x37 0xE8 0x8F 
                                    0x37 0xAE 0xCE 0x9E 0xE5 0xDF 0x5E 0x00 
~~~

3. Conficura el puerto `Gig0/1` en modo **troncal**

~~~
S1(config)#interface GigabitEthernet 0/1
S1(config-if)#switchport mode trunk 
~~~

4. Configura el switch S como **cliente** dentro del protocolo **VTP**

~~~
Switch#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#vtp domain vlan
Domain name already set to vlan.
Switch(config)#vtp password 1234
Setting device VLAN database password to 1234
Switch(config)#vtp mode client
Device mode already VTP CLIENT.
~~~

5. Muestra el estado del protocolo **VTP** en el switch S2

~~~
S2#show vtp status
VTP Version capable             : 1 to 2
VTP version running             : 2
VTP Domain Name                 : vlan
VTP Pruning Mode                : Disabled
VTP Traps Generation            : Disabled
Device ID                       : 0002.4A5B.B300
Configuration last modified by 0.0.0.0 at 3-1-93 00:04:22

Feature VLAN : 
--------------
VTP Operating Mode                : Client
Maximum VLANs supported locally   : 255
Number of existing VLANs          : 8
Configuration Revision            : 1
MD5 digest                        : 0xBB 0x52 0x2E 0x29 0x84 0x37 0xE8 0x8F 
                                    0x37 0xAE 0xCE 0x9E 0xE5 0xDF 0x5E 0x00 
~~~


6. Configura el puerto `Gig0/1`del switch S2 en modo **troncal**

~~~
S2(config)#interface GigabitEthernet 0/1
S2(config-if)#switchport mode trunk 
~~~

7. Muestra un resumen de las redes vlan del switch S2 (no debe haber ninguna vlan salvo la que se crea por defecto)

~~~
S2#show vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/1, Fa0/2, Fa0/3, Fa0/4
                                                Fa0/5, Fa0/6, Fa0/7, Fa0/8
                                                Fa0/9, Fa0/10, Fa0/11, Fa0/12
                                                Fa0/13, Fa0/14, Fa0/15, Fa0/16
                                                Fa0/17, Fa0/18, Fa0/19, Fa0/20
                                                Fa0/21, Fa0/22, Fa0/23, Fa0/24
                                                Gig0/2
10   proyecto10                       active    
20   proyecto20                       active    
30   proyecto30                       active    
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active   
~~~

8.Conecta los puertos `Gig0/1` de ambos switches.

9. Muestra un resumen de las redes vlan del switch S2. ¿Qué diferencia hay ?

~~~
La diferencia esta que nos ha llevado con el VTP solo las VLAN'S para que asi se propagen y se puedan configurar en otro switch
~~~

~~~
S2#show vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/1, Fa0/2, Fa0/3, Fa0/4
                                                Fa0/5, Fa0/6, Fa0/7, Fa0/8
                                                Fa0/12, Fa0/13, Fa0/14, Fa0/15
                                                Fa0/16, Fa0/17, Fa0/18, Fa0/19
                                                Fa0/20, Fa0/21, Fa0/22, Fa0/23
                                                Fa0/24, Gig0/2
10   proyecto10                       active    Fa0/9
20   proyecto20                       active    Fa0/10
30   proyecto30                       active    Fa0/11
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active 
~~~



# EJERCICIO-3

<center>

![](/img/ejercicio3.png)

</center>

Conectar un **router 1841** al switch 2 por el puerto `Fa0/1` del router.

1. Configuramos  el router para hacer enrutamiento entre VLANs (Router On A Stick). Para ello creamos sub-interfaces para cada vlan en el puerto `Fa0/1` del router:

+ Sub-interfaz para la vlan 10

~~~
R1(config)#interface FastEthernet 0/1.10
R1(config-subif)#encapsulation dot1Q 10
R1(config-subif)#ip address 10.0.10.10 255.255.255.0
~~~

+ Sub-interfaz para la vlan 20

~~~
R1(config)#interface FastEthernet 0/1.20
R1(config-subif)#encapsulation dot1Q 20
R1(config-subif)#ip address 10.0.20.1 255.255.255.0
~~~

+ Sub-interfaz para la vlan 30

~~~
R1(config)#interface FastEthernet 0/1.30
R1(config-subif)#encapsulation dot1Q 30
R1(config-subif)#ip address 10.0.30.1 255.255.255.0
~~~

2. Configuramos la interfaz `Fa0/0` con un servidor para hacer pruebas de conectividad. Utiliza las `ips` de la red `192.168.1.0/2` para esta nueva red.

~~~
Router(config)#interface FastEthernet 0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
~~~

3. Muestra la tabla de enrutamiento del router.

~~~
Router#show ip route
Codes: C - connected, S - static, I - IGRP, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     10.0.0.0/24 is subnetted, 3 subnets
C       10.0.10.0 is directly connected, FastEthernet0/1.10
C       10.0.20.0 is directly connected, FastEthernet0/1.20
C       10.0.30.0 is directly connected, FastEthernet0/1.30
C    192.168.1.0/24 is directly connected, FastEthernet0/0
~~~

4. Guarda la configuración del router.

~~~
R1#copy running-config startup-config 
~~~
