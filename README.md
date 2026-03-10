

# PRACTICAL NO 1

## AIM :-
Understanding the Sensor Node Hardware. (For Eg. Sensors, Nodes(Sensor mote), Base Station,Graphical User Interface.)

---

## STEPS :-
1. Identify the main components of a Wireless Sensor Network:
   - Sensors
   - Sensor Node / Mote
   - Base Station
   - Graphical User Interface (GUI)

2. Study Sensors and their types used in real applications.

3. Understand the working of Sensor Mote (processing + memory + radio unit).

4. Study Base Station role in collecting data from sensor nodes.

5. Understand how GUI is used to monitor, visualize and control the network.

## OUTPUT :-
- Sensor node hardware components and their roles were understood.

---

# PRACTICAL NO 2

## AIM :-
Exploring and understanding TinyOS computational concepts:
- Events, Commands and Task.
- nesC model
- nesC Components

---

## STEPS :-
1. Study TinyOS as an event-driven operating system used for WSN.

2. Understand:
   - Events (asynchronous)
   - Commands (synchronous)
   - Tasks (deferred execution)

3. Understand nesC programming model:
   - Components
   - Interfaces
   - Wiring

4. Study types of nesC components:
   - Modules (implementation)
   - Configurations (wiring/connection)

## OUTPUT :-
- TinyOS computational concepts and nesC component model were understood.

---

# PRACTICAL NO 3

## AIM :-
Create and simulate a simple adhoc network.

---

## STEPS :-
1. From the bottom toolbar, click on Network Devices then Wireless Devices and select AP-PT Access Point.

2. From End Devices, select PC and place 5 PCs on the screen.

3. Click on each PC, go to Physical section, turn off power, replace the ethernet port with PT-HOST-NM-1W, and turn power back on.

4. Repeat for every PC until all are connected wirelessly.

## OUTPUT :-
- Successfully connected every device to the Access Point.

---

# PRACTICAL NO 4

## AIM :-
Understanding, Reading and Analyzing Routing Table of a network.

---

## STEPS :-
1. Select 3 Routers (1841), 3 switches (2960-24TT), and 5 PCs. Connect them using Automatically Choose Connection Type.

2. Add Serial Interfaces to routers:
   - In Physical section, turn off power
   - Add WIC-2T port
   - Turn on power

3. Connect Routers using Serial DCE wire (Serial0/0/0 to Serial0/0/1).

4. Configure IP addresses for Router0, Router1, and Router2.

5. Configure IP addresses for all PCs.

6. Configure Routers using CLI mode to establish routing.

7. Check connections using the ping command or simulation mode.

## OUTPUT :-
- Successfully connected and verified routing between all devices.

---

# PRACTICAL NO 5

## AIM :-
Create a basic MANET implementation simulation for Packet animation and Packet Trace.

---

## STEPS :-
1. Select 1 Wireless Router (WRT300N) and 5 Laptops.

2. For each laptop:
   - Turn off power
   - Replace ethernet port with PT-LAPTOP-NM-1W
   - Turn on power

3. Ensure all laptops establish a wireless connection to the router.

## OUTPUT :-
- Successfully connected every device for MANET simulation.

---

# PRACTICAL NO 6

## AIM :-
Implement a Wireless sensor network simulation.

---

## STEPS :-
1. Select AP-PT Access Point, Server-PT, 2 PCs, and 1 Laptop.

2. Configure Laptop:
   - Replace ethernet with PT-LAPTOP-NM-1W

3. Configure PCs:
   - Replace ethernet with PT-HOST-NM-1W

4. Configure Server:
   - Replace ethernet with PT-LAPTOP-NM-1W

5. Power on all devices and verify wireless connection to the AP.

## OUTPUT :-
- Successfully connected all sensor network components.

---

# PRACTICAL NO 7

## AIM :-
Create MAC protocol simulation implementation for wireless sensor Network.

---

## STEPS :-
1. Select Wireless router- WRT300N Router, 3 Laptops, 2 Smartphones, and 1 Tablet.

2. Make Laptops wireless using the PT-LAPTOP-NM-1W module.

3. Go to the Config tab of a Laptop/Tablet and copy its MAC address from the Wireless0 interface.

4. In Router settings, go to GUI -> Wireless -> Wireless MAC Filter.

5. Enable the filter and select:
   - Prevent PCs listed below from accessing the wireless network

6. Enter the copied MAC addresses and save settings.

## OUTPUT :-
- Devices with specified MAC addresses lose connection to the router.

---

# PRACTICAL NO 8

## AIM :-
Simulate Mobile Adhoc Network with Directional Antenna.

---

## STEPS :-
1. Select 1 Fan, 1 Door, 1 Light, 1 Motion Detector, 1 Smartphone, and 1 Home Gateway.

2. For IoT devices (Fan, Light, etc.):
   - Go to Advanced -> I/O Config
   - Change adapter to PT-IOT-NM-1W

3. In Config tab, set IoT Server to Home Gateway.

4. Copy SSID from Home Gateway Wireless settings and paste into Smartphone Wireless0 settings.

5. Copy LAN IP of Home Gateway; open Smartphone web browser and navigate to that IP.

6. Login with admin/admin.

7. Create Conditions (Rules) for FanOn, FanOff, LightOn, etc., based on motion detector status.

8. Test by holding Ctrl+Alt and hovering over the motion detector.

## OUTPUT :-
- Automated responses based on sensor conditions were observed.

---

# PRACTICAL NO 9

## AIM :-
Create a mobile network using Cell Tower, Central Office Server, Web browser and Web Server.

---

## STEPS :-
1. Select WRT-300N Router, 1 PC, 1 Server-PT, 1 Smartphone, 1 Cell Tower, and 1 Central-Office-Server.

2. Connect Cell Tower and Central-Office-Server using Coaxial wire.

3. Make Server and PC wireless using PT-HOST-NM-1W.

4. On Server, set Wireless IP to DHCP and copy the IPv4 address.

5. On Smartphone, open Web Browser and enter the Server's IP.

6. On Smartphone, copy its own IPv4 address from IP configuration.

7. On PC, use Command Prompt to ping the Smartphone’s IP address.

## OUTPUT :-
- Successful connectivity between mobile network components was verified.

---



[A.pdf](https://github.com/user-attachments/files/25857642/A.pdf)

