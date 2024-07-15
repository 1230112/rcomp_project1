### Sprint master: it was supossed to be 1201262, but he didn't answered to the messages at the end, so student 1230112, will try to do a planning ###

# 1. Sprint's backlog #

- **T.3.1** - Update the building1.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 1.

- **T.3.2** - Update the building2.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 2. Final integration of each member's Packet Tracer simulation into a single simulation (campus.pkt).

- **T.3.3** - Update the building3.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 3.


# 2. Technical decisions and coordination #

## 2.1 OSPF area IDs ##


**OSPF area IDs** 

|Student Number|   Building    |       IP      |
|:------------:|:-------------:|:-------------:|
|   1230112    |   Backbone    |       0       |
|   1230112    |       1       |       1       |   
|   1211720    |       2       |       2       |
|   1201261    |       3       |       3       |


## 2.2 VoIP
 
|Student Number|   Building    |    Floor 0    |    Floor 1    |
|:------------:|:-------------:|:-------------:|:-------------:|
|   1230112    |       1       |     1000      |      1001     |
|   1211720    |       2       |   2000        |      2001     |
|   1201261    |       3       |   3000        |      3001     |


## 2.3 DHCPv4 Service

A **DHCPv4 Service**

| Building Name  | **Floor 0 Network** | **Floor 1 Network** | **WiFi Network** | **VoIP Network** |
|:--------------:|:-------------------:|:-------------------:|:----------------:|:----------------:|
| **Building 1** |     NETWORK_B1_F0   |     NETWORK_B1_F1    |      NETWORK_B1_WIFI     |      NETWORK_B1_VOIP    |
| **Building 2** |      NETWORK_B2_F0   |     NETWORK_B2_F1    |      NETWORK_B2_WIFI     |      NETWORK_B2_VOIP    |
| **Building 3** |      NETWORK_B3_F0   |     NETWORK_B3_F1    |      NETWORK_B3_WIFI     |      NETWORK_B3_VOIP    |

## 2.4 DNS Domains


**General Domain Names:**

* **Highest-Level Domain**: rcomp-23-24-de_e-g4
* **Server**: server1.rcomp-23-24-de_e-g4
* **Web**: web.rcomp-23-24-de_e-g4
* **WWW**: www.rcomp-23-24-de_e-g4

| Building Name |        **Local DNS**        |
|:--------------:|:---------------------------:|
| **Building 1** |      rcomp-23-24-de_e-g4      |
| **Building 2** | building-2.rcomp-23-24-de_e-g4 |
| **Building 3** | building-3.rcomp-23-24-de_e-g4 |

|   Building Name   | **DNS Server IPv4** |
|:-----------------:|:-------------------:|
|  **Building 1**   |     172.22.244.2      |








