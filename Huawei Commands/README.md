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


