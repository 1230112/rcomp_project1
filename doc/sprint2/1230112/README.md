# SPRINT 2 - RCOMP 1230112 - Elena Molero Padilla #
## - Configuration of devices (important comments)
- SWITCH_MC:
>  At least one switch must be in server mode (vtp mode server), so this will be. 
>
>I will use 8 modules PT-SWITCH-NM-1FGE (to provide a strong connectivity, since it has one gigabit interface converter) and for the rest of opennings PT-SWITCH-NM-COVER,since the cover plate provides protection for the internal electronic components. It also helps maintain adequate cooling by normalizing airflow. In the future you can change it, if you want to add more ports.
>
>I have considered that putting a password would be nice for this important switch. The password is: g004.

- ROUTER_B1:
>Model 2811 with a module NM-1FE-FX. This module provides one Fast-Ethernet interface for use with fiber media. Ideal for a wide range of LAN applications, the Fast Ethernet network modules support many internetworking features and standards. Single port network modules offer autosensing 10/100BaseTX or 100BaseFX Ethernet.
>
>With this new interface FastEthernet1/0, we will create logical subinterfaces for the 6 networks.

>#### IP ADDRESS
>BACKBONE 172.22.240.1/24
>
>A_DMZ 172.22.244.1/25 
>
>A_OUTLETS_F0 172.22.245.129 255.255.255.192
>
>A_OUTLETS_F1 172.22.245.193 255.255.255.192
>
>A_WIFI 172.22.244.129 255.255.255.128
>
>A_VOIP 172.22.245.1 255.255.255.128

- END DEVICES
>#### IP ADDRESS
> PC_F0_B1_1 172.22.245.130 255.255.255.192
>
>LAPTOP_F1_B1_1 172.22.244.130 255.255.255.128
>
>PC_F1_B1_1 172.22.245.194 255.255.255.192
>
>SERVER_B1 172.22.244.2 255.255.255.128

## - Static Routing
>In ROUTER_ISP, we set that as default packets will go to the interfaceof the ROUTER_B1.
>
>In ROUTER_B1 we will lead to the different buildings depending of their ip address block. This will be done through the backbone subinterface of each building. As default, it will send the info to the ROUTER_ISP.
>
>In ROUTER_B2 if the ip address is in the block of building 3, we will send to it through the backbone subinterface of building 3. Otherwise, it will go the the ROUTER_B1.
>
>In ROUTER_B3 if the ip address is in the block of building 32 we will send to it through the backbone subinterface of building 2. Otherwise, it will go the the ROUTER_B1.