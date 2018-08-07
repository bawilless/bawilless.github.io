## Getting Started

This page will guide you through updating your MT3620 development board, claiming it to a tenant, enabling development/debug mode, and setting up Wifi.  After you complete these steps you will be able to download and run applications on the development board.

### Required Tools

In order to complete the labs, you'll need to have a couple of tools installed on your laptop.

- Visual Studio 2017 version 15.7 or greater

  - Visual Studio 2017 Community (free) version is fine

- The instructor will pass around thumb drives with the required files

  - Unzip all the TP 4.2 Files into one directory.  This will unpack two additional zip files MT3620DeviceUPdate.zip and MT3620WifiRegion.zip.  Unzip MT3620DeviceUpdate.zip into the \Customer Drop TP4.2 directory.
  
- Run and install VS_Tools_Preview_For_Azure_Sphere.exe

- The instructor will pass out development kits for each student

  - You are welcome to use your own MT3620 however, **you must claim your board to your own tenant.**

### Update MT3620 Development Board
- Connect MT3620 board over USB

- Start the "Azure Sphere Developer Command Prompt Preview" application under Programs -> Azure Sphere

- Change directory to (your location)\Customer Drop TP4.2\MT3620 Device Update\Images

- Update the board using the command 

  - ```azsphere dev recover -i .``` to update the board

### Claim Device

- Still in the "Azure Sphere Developer Command Prompt Preview" window, use the command:

  - ```azsphere login```
  
  - Login as a Bootcamp Azure Sphere user.  Login credentials can be found in your student hardware kit.

- claim your device with command: 

  - ```azsphere device claim```
  
  - The device will be claimed to the ```SDEStudentTrain77``` tenant.

### Set Board to Debugging Mode

- Set development board up for development and debugging.  This will allow the developer to "side load" applications over the USB connection.  Set the board to debug mode with the command:

  - ```Azsphere device prep-debug```
  
  - Note:  If this command fails, try to claim the device a second time, then try again.

### Assign Board to the System Software Group

- Use command to list all groups:

  - ```azsphere dg list```  

  - Copy the ID of the group "System Software" 
  
  - System Software should have ID: ```63bbe6ea-14be-4d1a-a6e7-03591d882b42```
  
  - Add device to this group with command:

    - ```azsphere device update-devicegroup -d 63bbe6ea-14be-4d1a-a6e7-03591d882b42```

- Set the Wifi Region (only needed once on older devices) from the MT3620WifiRegion directory

  - \Customer Drop TP4.2\MT3620WifiRegion> ```Mt3620WifiRegion US```

### Setup WiFi

- Set up WiFi 

  - ```azsphere dev wifi add -s IOTDEMO -k iotDemo1```

- Check WiFi status with command:

  - ```azsphere dev wifi show-status```
