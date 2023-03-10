# Navigating the CLI

- Change view to system and interface view
  ```
  <Huawei>system-view 
  Enter system view, return user view with Ctrl+Z.
  
  [Huawei]interface g0/0/0
  [Huawei-GigabitEthernet0/0/0]
  ```
  
- change router name [in system view] 
  ```
  <Huawei>system-view 
  Enter system view, return user view with Ctrl+Z.
  
  [Huawei]sysname Router1
  ```

- setup date [user view CTRL Z]
  ```
  <Router1>clock timezone GMT add 02:00:00

  <Router1>clock datetime 03:00:00 2001-12-19

  <Router1>display clock 
  2001-12-19 03:00:16
  Wednesday
  Time Zone(GMT) : UTC+02:00
  ```
  
- messages of login [system view]  
  ```
  <Router1>system-view 
  Enter system view, return user view with Ctrl+Z.
 
  [Router1]header login information "Enter password"

  [Router1]header shell information "Login successfully"
  ```
- set up password to the router
  ```
  <Router1>system-view 
  Enter system view, return user view with Ctrl+Z.

  [Router1]user-interface console 0

  [Router1-ui-console0]set authentication password cipher 123
  [Router1-ui-console0]

  Configuration console exit, please press any key to log on
  Enter password
  Login authentication
  Password:
  Login successfully
  ```
- add ip to Interface  
  ```
  <Huawei>system-view 
  Enter system view, return user view with Ctrl+Z.
  
  [Huawei]sysname Router
  
  [Router]interface g0/0/0
  [Router-GigabitEthernet0/0/0]ip add 10.0.12.1 24

  [Router-GigabitEthernet0/0/0]quit

  [Router]interface LoopBack 0
  [Router-LoopBack0]ip add 1.1.1.1 32
  [Router-LoopBack0]
  ```
# Establishing a Single Switched Network 

- display mac address table [switch]
  ```
  display mac-address 
  ```

# IP Static Routes 



- Draw static route bewtween router and network (last octet is 0)[draw 2 wayes to enable pinging]
  
  ![Screenshot 2022-12-25 215228](https://user-images.githubusercontent.com/99830416/209480455-92d134f9-3ee4-474f-a4f1-7ee091d9d4b8.png)

  ```
  [ip route_static] [destenation_ip] [subnet_mask] [next_hope(interface of second router)]
  ip route-static 192.168.2.0 24 10.0.12.2
  ```


- display routing table [router - user view].
  ```
  display ip routing_table
  ``` 

- Default Static Routes
 
  ![Screenshot 2022-12-25 215118](https://user-images.githubusercontent.com/99830416/209480399-1d6b9878-fe71-4285-b0d5-695891aa994f.png)

 # OSPF
 
 -  ospf config
 
    ```
    [R1]ospf 1 router-id 10.0.1.1 
    [R1-ospf-1]area 0 
    [R1-ospf-1-area-0.0.0.0]network 10.0.1.0 0.0.0.255 
    ```
 
 
 - Change network type of the router interface 
    ```
    [RTD]interface GigabitEthernet0/0/0
    [RTD-GigabitEthernet0/0/0]ospf network-type p2p
    ```
  
- set cost to OSPF  
  ```
  [RTA]interface GigabitEthernet 0/0/0
  [RTA-GigabitEthernet0/0/0]ospf cost 20   
  ```
# FTP 

- enable ftp server in any router 
  ```
  [R1]ftp server enable
  [R1]set default ftp-directory flash:/
  ```
  
# dhcp 
  
- global


- interface  
  ```
  [Huawei]dhcp enable
  [Huawei]interface GigabitEthernet0/0/0
  [Huawei-GigabitEthernet0/0/0]dhcp select interface  
  ```
