Goal: 
Not allow more than 1 MAC address to be learned on port GigabitEthernet0/1

How: configure port security on g0/1 with violation mode restrict, max addresses 1, and an aging time of 30 minutes.  

Verification: connect 1 PC to the switch and see if it learns the address. Then connect another PC to the same port with a different mac address
and see the frames discarded with the violation counter increasing and syslog messages generated. 


configuration: 


interface GigabitEthernet0/1
 switchport access vlan 100
 switchport mode access
 switchport port-security violation restrict
 switchport port-security aging time 10
 switchport port-security