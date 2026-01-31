# Aryzta Automated Pick-and-Pack System

This project simulates a fully automated pick-and-pack production line inspired by **Aryzta**, a global leader in frozen bakery manufacturing. Using MATLAB, a UR3e robot on a linear rail, and a custom-designed Pancake Picker Arm, the system demonstrates robotic manipulation, conveyor synchronisation, collision detection, and integrated industrial safety systems suitable for food-processing environments.

---

## Project Abstract

This project presents the design and simulation of an automated robotic pick-and-pack system for frozen pancake packaging, inspired by real-world Aryzta production lines. The system integrates two robotic manipulators: a UR3e industrial robot mounted on a linear rail and a custom-designed Pancake Picker Arm. Pancakes are transported via a continuously moving conveyor and autonomously intercepted, picked, and packed into boxes.

The simulation incorporates trajectory planning, real-time robot control, collision detection, and multiple safety mechanisms, including a simulated light curtain, emergency stop functionality, and human–robot interaction monitoring. A MATLAB-based graphical user interface enables manual jogging, system control, and emergency recovery. The project demonstrates key robotics concepts including kinematic modelling, planning, safety integration, and user interaction, aligned with the learning outcomes of Robotics 41013.

---

## Background: Aryzta & Industrial Pick-and-Pack

Aryzta AG is an international food company specialising in frozen bakery products supplied to supermarkets and quick-service restaurants worldwide. Their production lines rely heavily on automation to:

- Increase throughput and consistency  
- Reduce manual labour in cold environments  
- Improve worker safety  
- Maintain food hygiene standards  

This project models a simplified Aryzta-style pick-and-pack line where pancakes are transported on a conveyor, picked by robots, and placed into boxes while reacting to safety events and human interaction.

---

## Project Videos

**Main Demonstration**  
https://www.youtube.com/watch?v=sB-ZhjLr7Xw  

**Short Highlight**  
https://youtu.be/PXZmRQ2L8Qg?si=wORxRKe22PVtkBLa  

---

## Repository Structure

aryztaPicknPack/

│── Box and Pancake Movement/ # Pancake motion and box placement logic

│── Environment/ # Conveyor, light curtain, safety models

│── GUI/ # Graphical user interface controls

│── RobotArm/ # UR3e and custom Pancake Picker Arm models

│── Main.m # Main simulation entry point

│── README.md # Project documentation


---

## System Architecture

### Block Diagram (Conceptual)


**GIF / Image Placeholder – System Block Diagram**  
![System Block Diagram](media/diagrams/system_block_diagram.svg)

---

## Project Breakdown

### 1. Robot Subsystem

#### 1.1 UR3e on Linear Rail
A UR3e industrial robot model extended with a linear rail to increase workspace coverage and allow early interception of moving pancakes.

- Custom 7-link kinematic model  
- Linear rail implemented via base transformation  
- Smooth joint-space trajectories  
- Predictive motion planning  

**GIF – UR3e Moving Along Linear Rail**  
![UR3e Linear Rail](media/gifs/ur3e_linear_rail.gif)

---

#### 1.2 Pancake Picker Arm
A custom-designed robotic arm specialised for fast and gentle pancake handling.

- Designed for flat food items  
- Simulated food-safe manipulation  
- Performs final placement into boxes  

**GIF – Pancake Picker Arm Operation**  
![Pancake Picker Arm](media/gifs/pancake_picker.gif)

---

### 2. Conveyor and Pancake Movement

#### 2.1 Continuous Pancake Flow
Pancakes move continuously without stopping, requiring synchronised robot motion.

- Non-blocking, time-based updates  
- Robot timing synchronised with conveyor speed  
- Arduino-style `millis()` logic (no pause or busy loops)  

**GIF – Conveyor with Moving Pancakes**  
![Conveyor and Pancake Movement](media/gifs/conveyor_flow.gif)


---

#### 2.2 Box Placement
Boxes are positioned to receive pancakes from the picker arm.

- Fixed target locations  
- Controlled drop poses  

---

### 3. Environment and Safety

#### 3.1 Factory Environment
The simulated workspace includes:

- Conveyor belts  
- Work tables  
- Safety zones  
- Light curtain  

**GIF – Full Environment Overview**  
![Environment and Safety](media/gifs/full_environment.gif)

---

#### 3.2 Light Curtain Safety System
A simulated industrial light curtain monitors human intrusion.

- Triggered when a human crosses the safety plane  
- Instantly stops robots and conveyor  
- Requires manual reset before resuming  

**GIF – Light Curtain Triggered by Human**  
![Light Curtain Safety System](media/gifs/light_curtain_stop.gif)

---

### 4. Human Interaction and Collision Detection

- Animated human model scaled to 0.8  
- Collision detection via proximity checks  
- Emergency stop triggered on unsafe approach  
- System enters safe state until reset  

---

### 5. GUI and User Control

The MATLAB GUI provides:

- Start/stop control of robots and conveyor  
- Emergency stop activation  
- System state and safety feedback  
- Manual interaction for demonstration  

**GIF – GUI Operation**  
![GUI and User Control](media/gifs/gui_control.gif)

---

## Alignment with Robotics 41013 Marking Criteria

This project addresses the key assessment requirements:

- **Two interacting robot arms** (UR3e + custom arm)  
- **Custom robot modelling** (non-toolbox arm)  
- **Trajectory planning and RMRC-style control**  
- **Collision detection and avoidance**  
- **Simulated safety systems (light curtain, e-stop)**  
- **GUI with user interaction and recovery after stop**  
- **Realistic industrial environment**  
- **Code structured for individual viva examination**

---

## Running the Simulation

1. Clone the repository:
   ```bash
   git clone https://github.com/abaeljoseph/aryztaPicknPack
   
2. Open MATLAB and add files to path:

   ```bash
   addpath(genpath(pwd))
   
3. Run the simulation:

   ```bash
   Main
## Technical Highlights

- Custom UR3e MATLAB class
- Linear rail extension
- State-machine based timing
- Collision detection and safety logic
- Non-blocking real-time animation
- Modular folder structure

## Contributors

Developed by:

— Abael Joseph

— Samir Safarjlani

— Nikhil Sudhir

**University of Technology Sydney — Mechatronics Engineering**
