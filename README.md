

# PRACTICAL NO 1

## AIM :-
Understanding the Sensor Node Hardware. (For Eg. Sensors, Nodes(Sensor mote), Base Station, Graphical User Interface.) 

---

## STEPS :-
1. Sensor node hardware ke main components identify karo: **Sensors, Motes/Nodes, Base Station, GUI**.
2. Architecture samjho: **Perception Layer, Network Layer, Application Layer**.
3. Applications list karo: Environmental Monitoring, Healthcare, Industrial IoT.
4. Challenges note karo: power consumption, scalability, security.
## OUTPUT :-
- Sensor node hardware ka overview clear hua aur WSN design perspective samjha. 

---

# PRACTICAL NO 2

## AIM :-
Exploring and understanding TinyOS computational concepts:
- Events, Commands and Task.
- nesC model
- nesC Components

---

## STEPS :-
1. **Events**: asynchronous signals (example: Timer fired type behavior).
2. **Commands**: synchronous calls between components.
3. **Tasks**: deferred computations executed sequentially (scheduler based).
4. **nesC model**: **Modules (logic)** and **Configurations (wiring)**.

## OUTPUT :-
- TinyOS + nesC ka component-based approach aur event-driven model samjha. 

---

# PRACTICAL NO 3

## AIM :-
Create and simulate a simple adhoc network. 

---

## STEPS :-
1. Bottom toolbar se **Network Devices → Wireless Devices** me jaake **AP-PT (Access Point)** place karo.
2. **End Devices** se **PC** select karke total **5 PCs** place karo.
3. Har PC par: **Physical** tab → power off → ethernet module replace with **PT-HOST-NM-1W** → power on.
4. Sab PCs ko wireless connect karke AP association verify karo.
## OUTPUT :-
- Successfully sab devices Access Point se connect ho gaye.
---

# PRACTICAL NO 4

## AIM :-
Understanding, Reading and Analyzing Routing Table of a network.

---

## STEPS :-
1. **3 Routers (1841)**, **3 Switches (2960-24TT)**, **5 PCs** place karke auto connection se connect karo.
2. Router me serial interface add: **Physical** tab → power off → **WIC-2T** add → power on.
3. Routers ko **Serial DCE** wire se connect karo (Serial0/0/0 ↔ Serial0/0/1).
4. Routers ko IP addressing do (Router0/1/2).
5. PCs ko IP addressing do.
6. CLI me routing configure karo.
7. `ping`/simulation se connectivity verify karo. 

## OUTPUT :-
- Routing established hua aur end-to-end connectivity verify hui.

---

# PRACTICAL NO 5

## AIM :-
Create a basic MANET implementation simulation for Packet animation and Packet Trace.

---

## STEPS :-
1. **1 Wireless Router (WRT300N)** aur **5 Laptops** place karo.
2. Har laptop me: power off → ethernet replace with **PT-LAPTOP-NM-1W** → power on.
3. Wireless connection establish karke packet animation/trace observe karo. 

## OUTPUT :-
- MANET simulation setup me devices successfully connected.

---

# PRACTICAL NO 6

## AIM :-
Implement a Wireless sensor network simulation.
---

## STEPS :-
1. **AP-PT**, **Server-PT**, **2 PCs**, **1 Laptop** place karo.
2. Laptop me wireless module set karo (**PT-LAPTOP-NM-1W**).
3. PCs me wireless module set karo (**PT-HOST-NM-1W**).
4. Server me wireless module set karo (**PT-LAPTOP-NM-1W** as per journal).
5. Wireless association verify karo.
## OUTPUT :-
- Wireless sensor network simulation successfully connected.

---

# PRACTICAL NO 7

## AIM :-
Create MAC protocol simulation implementation for wireless sensor Network. 

---

## STEPS :-
1. **WRT300N**, **3 Laptops**, **2 Smartphones**, **1 Tablet** place karo.
2. Laptops ko wireless modules se enable karo.
3. Device ka **Wireless0 MAC address** copy karo.
4. Router GUI → Wireless → **Wireless MAC Filter** open karo.
5. Filter enable karke policy select karo (prevent listed devices).
6. MAC addresses add karke save karo.

## OUTPUT :-
- Listed MAC wale devices ka connection block/disconnect observe hua. 

---

# PRACTICAL NO 8

## AIM :-
Simulate Mobile Adhoc Network with Directional Antenna.

---

## STEPS :-
1. **Fan, Door, Light, Motion Detector, Smartphone, Home Gateway** place karo.
2. IoT devices me adapter **PT-IOT-NM-1W** set karo.
3. IoT Server/Home Gateway mapping configure karo.
4. Smartphone ko SSID ke through connect karo.
5. Gateway LAN IP browser me open karke login (`admin/admin`).
6. Conditions/Rules create karke motion detector se automation test karo. 

## OUTPUT :-
- Motion detect hone par automated actions (fan/light rules) observe hue.

---

# PRACTICAL NO 9

## AIM :-
Create a mobile network using Cell Tower, Central Office Server, Web browser and Web Server.

---

## STEPS :-
1. **WRT-300N**, **PC**, **Server-PT**, **Smartphone**, **Cell Tower**, **Central-Office-Server** place karo.
2. Cell Tower ↔ Central Office Server coaxial se connect karo.
3. Server aur PC ko wireless module se connect karo.
4. Server DHCP se IP lo aur IPv4 copy karo.
5. Smartphone browser me server IP open karo.
6. Smartphone ka IPv4 copy karke PC se ping test karo. 
## OUTPUT :-
- Mobile network components ke beech connectivity successfully verify hui.

---
