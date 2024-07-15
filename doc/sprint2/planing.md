# SPRINT 2 - RCOMP #
### In this Sprint, the student number 1230112 will be the sprint master. ###
## DECISIONS TAKEN IN THIS SPRINT ##
## - Retrospective ##
After the demostration of Sprint 1 with the client, we have to change:
- For each cross-conected we will have UPS.
- All members of the team will use less CPs. In case of Building 1, student 1230112 won't use CP, as the building is small, and using them could become in interferences. This building don't need them, although she use them to do easier and cheaper changes in the future. The rest of the group will also reduce the CPs.
- In the room dedicated as data-center, student 1230112 put outlets because maybe in the future it could change. This way we will be prepare.
- We should use only one IC per building. We put double cable between floors, but we made the mistake putting one IC per floor. Finally, we will keep the double cable redundancy (fiber cable ) but no the double IC per building.

## - Backlog ##
- 1230112 student: being the sprint master so, do the planning and review. Development of a layer two and layer three Packet Tracer
simulation for building 1, encompassing the campus backbone.
Integration of every member’s Packet Tracer simulation into
a single simulation.
- 1211720 student: Development of a layer two and layer three Packet Tracer simulation for building 2, encompassing the campus backbone. Finish the tasks that he couldn't done last sprint.
- 1201262 student: Development of a layer two and layer three Packet Tracer
simulation for building 3, encompassing the campus backbone.

## - Cisco Packet Tracer Version ##
            Version 8.2.1.0118 
## - VLANIDs and their names ##
The range our team can use for the VLANIDs is: 371-392 

|BUILDING|VLAN ID|VLAN NAME|
|:------:|:-----:|:-------:|
| Default| 1 | DEFAULT|
|   Backbone    | 371   |BACKBONE|
|   A    | 372   |A_OUTLETS_F0|
|   A    | 373   |  A_OUTLETS_F1  |
|   A    | 374   |  A_WIFI |
|   A    | 375   | A_DMZ |
|   A    | 376   | A_VOIP|
|   B    | 377   |B_OUTLETS_F0|
|   B    | 378   |  B_OUTLETS_F1  |
|   B    | 379   |  B_WIFI |
|   B    | 380   | B_DMZ |
|   B    | 381   | B_VOIP|
|   C    | 382   |C_OUTLETS_F0|
|   C    | 383   |  C_OUTLETS_F1  |
|   C    | 384   |  C_WIFI |
|   C    | 385   | C_DMZ |
|   C    | 386   | C_VOIP|
## - VTP Domain name ##
                r2324deg4

At least one switch must be in server mode (vtp mode server). This will be The switch in Building 1 for the MCC.

## - ISP router’s IPv4 node address ##
                5.60.37.130/30
The maximum number of IPv4 nodes in a network with prefix-length 30 is: 2
## - IPv4 address space to be used (Block of IPv4 addresses) ##
                172.22.240.0/20
The maximum number of IPv4 nodes in a network with prefix-length 20 is: 4094

### PLANING ###
- 1 network with up to 220 nodes (B_WIFI) -> prefix-24, 256 address space=0.0.1.0

- 2 networks with up to 200 nodes (BACKBONE and C_WIFI) -> prefix-24, 256 address space=0.0.1.0

- 1 network with up to 180 nodes (C_VOIP)-> prefix-24, 256 address space=0.0.1.0

- 1 network with up to 130 nodes (C_OUTLETS_F1)-> prefix-24, 256 address space=0.0.1.0

- 1 network with up to 120 nodes (B_OUTLETS_F1)-> prefix-25, 128 address space=0.0.0.128

- 2 netwrok with up to 110 nodes (B_VOIP and C_OUTLETS_F0)-> prefix-25, 128 address space=0.0.0.128

- 1 network with up to 100 nodes (A_DMZ)-> prefix-25, 128 address space=0.0.0.128

- 1 network with up to 90 nodes (B_OUTLETS_F0)-> prefix-25, 128 address space=0.0.0.128

- 1 network with up to 80 nodes (A_WIFI)-> prefix-25, 128 address space=0.0.0.128

- 1 network with up to 67 nodes (A_VOIP)-> prefix-25, 128 address space=0.0.0.128

- 3 networks with up to 50 nodes (A_OUTLETS_F0, A_OUTLETS_F1 and B_DMZ)-> prefix-26, 64 address space=0.0.0.64

- 1 netwrok with up to 45 nodes (C_DMZ)-> prefix-26, 64 address space=0.0.0.64


**Let's assign the addresses sequentially starting by smaller prefixes:**
- BACKBONE
segment address ip space 172.22.240.0/22

|NETWORK|NODES|NETWORK ADDRESS|NEXT NETWORK|
|:------:|:-----:|:-------:|:-------:|
|   BACKBONE  | 200   |172.22.240.0/24|  172.22.241.0   |

- BUIDING 1
segment address ip space 172.22.244.0/22

|NETWORK|NODES|NETWORK ADDRESS|NEXT NETWORK|
|:------:|:-----:|:-------:|:-------:|
|   A_DMZ  | 100   |172.22.244.0/25|  172.22.244.128  |
|   A_WIFI  | 80   |172.22.244.128/25|  172.22.245.0   |
|   A_VOIP  | 67   |172.22.245.0/25|  172.22.245.128   |
|   A_OUTLETS_F0  | 50   |172.22.245.128/26|  172.22.245.192   |
|   A_OUTLETS_F1  | 50   |172.22.245.192/26|  172.22.246.0   |

- BUILDING 2
segment address ip space 172.22.248.0/22

|NETWORK|NODES|NETWORK ADDRESS|NEXT NETWORK|
|:------:|:-----:|:-------:|:-------:|
|   B_WIFI  | 220   |172.22.248.0/24|  172.22.249.0   |
|   B_OUTLETS_F1  | 120   |172.22.249.0/25|  172.22.249.128   |
|   B_VOIP  | 110   |172.22.249.128/25|  172.22.250.0  |
|   B_OUTLETS_F0  | 90   |172.22.250.0/25|  172.22.250.128   |
|   B_DMZ  | 50   |172.22.250.128/26|  172.22.250.192   |

- BUILDING 3
segment address ip space 172.22.252.0/22

|NETWORK|NODES|NETWORK ADDRESS|NEXT NETWORK|
|:------:|:-----:|:-------:|:-------:|
|   C_WIFI  | 200   |172.22.252.0/24|  172.22.253.0   |
|   C_VOIP  | 180   |172.22.253.0/24|  172.22.254.0   |
|    C_OUTLETS_F1  | 130   |172.22.254.0/24|  172.22.255.0   |
|   C_OUTLETS_F0  | 110   |172.22.255.0/25|  172.22.255.128   |
|   C_DMZ  | 45   |172.22.255.128/26|  172.22.255.192   |

We don't have to do building 4, but it should also be there in a group with 4 elements.

## - Device Names ##
**MARGINAL NOTES**

        X = Number of the Building
        Y = Number of the floor
        DEV = NUMBER of unit
- **PC:**
  - PC_FY_BX_DEV

- **Router:**
  - ROUTER_MC
  - ROUTER_ISP
  - ROUTER_BX

- **Laptop:**
  - LAPTOP_FY_BX_DEV

- **Switch:**
  - SWITCH_MC
  - SWITCH_IC_BX
  - SWITCH_HC_FY_BX
  - SWITCH_CP_FY_BX_DEV

- **Phone:**
  - PHONE_FY_BX_DEV

- **Access-Point:**
  - AP_FY_BX_DEV

- **Server:**
  - SERVER_BX