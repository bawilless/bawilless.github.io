# Welcome to the Azure Sphere Bootcamp information page

This page contains usefull references that will be helpfull while you attend the Avnet Azure Sphere Bootcamp.

## Getting Started

In order to complete the labs, you'll need to have a couple of tools installed on your laptop.

- Visual Studio 2017 version 15.7 or greater
  - Visual Studio 2017 Community (free) version is fine
- Instructor will pass around thumbdrives with the required files
  - Unzip all the TP 4.2 Files into one directory.  Unzip the zip files as well into the same directory.
  - Run and install tools\VS_Tools_Preview_For_Azure_Sphere.exe
- The instructor will pass out development kits for each student
  - You are welcome to use your own MT3620 however, **you must claim your board to your own tennant**

## Prepare the MT3620 board

### Update MT3620 development board

- Connect MT3620 board over USB

- Start "Azure Sphere Developer Command Promt Preview" under Programs -> Azure Sphere

- Change directory to <your location>\Customer Drop TP4.2\MT3620 Device Update\Images

- Update the board using the command 
  
  - 'azsphere dev recover -i .' to update the board

### Claim your device on your AAD

- Still in the "Azure Sphere Developer Command Promt Preview" window, use the command:

  - 'azsphere login'

  - Login with Bootcamp Azure Sphere user.  Instructor will provide username and password.
  
  - claim your device with command: 'azsphere device claim'

### Set board to debugging mode

- Set development board up for development and debugging with command:

  - 'Azsphere device prep-debug'

### Assign board to the System Software group in your AAD

- Use command to list all groups:

  - 'azsphere dg list'  

- Copy the ID of the group "System Software" 
  
  - System Software should have ID: '63bbe6ea-14be-4d1a-a6e7-03591d882b42'

- Add device to this group with command:

  - 'azsphere device update-devicegroup -d 63bbe6ea-14be-4d1a-a6e7-03591d882b42'

- Set the Wifi Region (only needed once on older devices)  From the MT3620WifiRegion directory
  - \Customer Drop TP4.2\MT3620WifiRegion> './Mt3620WifiRegion US'

### Setup WiFi

- Set up WiFi 
  
 - 'azsphere dev wifi add s IOTDEMO -k iotDemo1'

- Check WiFi status with command:

  - 'azsphere dev wifi show-status'

