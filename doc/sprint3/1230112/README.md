
## Important
As I had problems with the acls in relation with the NAT configuration, I decided to attacht also and all version I had previusly of the ACL configuration and VOIP configuration. The name of the file is OLD_VERSION. Here I can demostrate the nat was correctly configure.
## ACL
ACLs:
101 - interface closer to the isp
100 - Backbone's subinterface
102 - DMZ 's subinterface
104 - rest of subinterfaces
1- Internal Spoofing

Applied to all subinterfaces excluding dmz.
![alt text](image.png)
![alt text](image-1.png)

For the backbone's subinterface
![alt text](image-7.png)
2. External spoofing
![alt text](image-2.png)
![alt text](image-3.png)

3. ICMP ECHO

![alt text](image-4.png)
![alt text](image-5.png)

4. DMZ IN

![alt text](image-6.png)

5. DHCPv4

![alt text](image-8.png)

6. TFTP

![alt text](image-10.png)

7. OSPF

![alt text](image-11.png)