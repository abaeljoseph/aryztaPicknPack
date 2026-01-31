# Aryzta Automated Pick-and-Pack System

This project simulates a fully automated pick-and-pack production line inspired by **Aryzta**, a global leader in frozen bakery manufacturing. Using MATLAB, a UR3e robot on a linear rail, and a custom-designed Pancake Picker Arm, this simulation demonstrates automated handling, conveyor synchronisation, and industrial safety systems commonly found in food-processing factories.

---

## Background: Aryzta & Industrial Pick-and-Pack

Aryzta AG is an international food company specialising in frozen bakery products supplied to supermarkets and quick-service restaurants. Their production lines rely heavily on automation to:

- Increase throughput and consistency  
- Reduce manual labour in cold environments  
- Improve worker safety  
- Maintain food hygiene standards  

This project models a simplified version of an Aryzta-style pick-and-pack line where pancakes are transported on a conveyor, picked by robots, and placed into boxes while reacting to safety events.

---

## Project Videos

Main Demonstration  
https://www.youtube.com/watch?v=sB-ZhjLr7Xw  

Short Highlight  
https://youtu.be/PXZmRQ2L8Qg?si=wORxRKe22PVtkBLa  

---

## Repository Structure

aryztaPicknPack/
- Box and Pancake Movement/   Pancake motion and box placement logic  
- Environment/               Conveyor, light curtain, safety models  
- GUI/                       Graphical user interface controls  
- RobotArm/                  UR3e and custom Pancake Picker Arm models  
- Main.m                     Main simulation entry point  
- README.md                  Project documentation  

---

## Project Breakdown

### 1. Robot Subsystem

#### 1.1 UR3e on Linear Rail
A UR3e robot model extended with a linear rail to increase reach and workspace coverage.

- Custom 7-link kinematic model  
- Linear rail implemented via base transformation  
- Smooth joint-space trajectories  
- Predictive motion to intercept moving pancakes  

GIF PLACEHOLDER – UR3e moving along linear rail

---

#### 1.2 Pancake Picker Arm
A custom-designed robot arm for fast and gentle pancake handling.

- Designed specifically for flat food items  
- Performs final pick-and-place into boxes  

GIF PLACEHOLDER – Pancake Picker Arm operation

---

### 2. Conveyor and Pancake Movement

#### 2.1 Continuous Pancake Flow
Pancakes move continuously without stopping.

- Non-blocking, time-based updates  
- Robot motion synchronised with conveyor speed  
- Arduino-style millis() logic (no pause loops)  

GIF PLACEHOLDER – Conveyor with moving pancakes

---

#### 2.2 Box Placement
Boxes are positioned to receive pancakes from the picker arm.

- Fixed placement targets  
- Controlled drop locations  

---

### 3. Environment and Safety

#### 3.1 Factory Environment
Simulated industrial workspace including:

- Conveyor belts  
- Work tables  
- Safety zones  
- Light curtain  

GIF PLACEHOLDER – Full environment overview

---

#### 3.2 Light Curtain Safety System
A simulated industrial light curtain monitors human intrusion.

- Triggered when a human crosses the safety plane  
- Instantly stops robots and conveyor  
- Requires manual reset to resume  

GIF PLACEHOLDER – Light curtain triggered by human

---

### 4. Human Interaction and Collision Detection

- Animated human model scaled to 0.8  
- Collision detection via proximity checks  
- Emergency stop triggered on unsafe approach  

---

### 5. GUI and User Control

The MATLAB GUI allows:

- Start/stop control of robots and conveyor  
- Emergency stop activation  
- System status feedback  

GIF PLACEHOLDER – GUI operation

---

## Running the Simulation

1. Clone the repository:
   git clone https://github.com/abaeljoseph/aryztaPicknPack

2. Open MATLAB and add files to path:
   addpath(genpath(pwd))

3. Run the simulation:
   Main

---

## Technical Highlights

- Custom UR3e MATLAB class  
- Linear rail extension  
- State-machine based timing  
- Collision detection and safety logic  
- Modular folder structure  

---

## Contributors

Developed by Abael Joseph, Samir Safarjlani, Nikhil Sudhir 
University of Technology Sydney  
Mechatronics Engineering
