# S.A.F.E.R SYSTEM  
## Smart, Adaptive, and Flexi-Elevating Roadbreaker System

The **S.A.F.E.R System** is a smart road safety prototype designed to detect vehicle speed, adapt to day and night conditions, elevate a roadbreaker for overspeeding vehicles, display real-time information, and send alerts to a mobile device through wireless communication.

The system is an Arduino-based closed-loop traffic control system that uses **two IR digital sensors** for vehicle detection and speed measurement, a **Grove Light Sensor** for day/night detection, an **Arduino Uno** as the main controller, an **ESP32** for wireless alerts, a **servo motor** for the roadbreaker mechanism, and a **16x2 LCD with I2C** for real-time output.

<img width="400" height="314" alt="image" src="https://github.com/user-attachments/assets/088fb5e4-c893-4df0-a292-4aa9d6333444" /> <img width="420" height="314" alt="IMG_3448" src="https://github.com/user-attachments/assets/94202d75-ba65-497e-ac49-32c8d11b1756" />



---

# I. OBJECTIVES

## General Objective
To design and implement a smart and adaptive roadbreaker prototype that improves road safety by automatically responding to overspeeding vehicles based on measured vehicle speed and environmental lighting conditions.

## Specific Objectives
- To detect moving vehicles using two IR sensors.
- To calculate vehicle speed using the time interval between the two IR sensor detections.
- To identify day and night operating conditions using a Grove Light Sensor.
- To implement adaptive speed limits for day mode and night mode.
- To activate a servo motor that elevates the roadbreaker when overspeeding is detected.
- To display speed, system mode, and status messages on a 16x2 LCD with I2C.
- To send mobile alerts through ESP32 using Wi-Fi communication.
- To integrate sensing, control, actuation, and communication into one working embedded system prototype.

---

# II. PROJECT DESCRIPTION

The **S.A.F.E.R System** stands for **Smart, Adaptive, and Flexi-Elevating Roadbreaker System**. It is a prototype traffic safety system designed to reduce overspeeding by making the roadbreaker respond only when necessary.

The system works by placing **two IR sensors** along a fixed path. When a vehicle passes the first sensor and then the second sensor, the Arduino Uno measures the time difference and calculates the vehicle speed over a known distance. A **Grove Light Sensor** reads ambient brightness and determines whether the system is operating in day mode or night mode. This allows the speed limit threshold to adapt according to environmental conditions. The proposal describes this as a closed-loop traffic control approach that dynamically adjusts the roadbreaker mechanism based on speed and lighting conditions.

The **Arduino Uno** acts as the primary controller. It receives data from the IR sensors and the light sensor, computes speed, compares the measured speed to the threshold, updates the display, and controls the servo motor. If the measured speed exceeds the limit, the **servo motor** elevates the roadbreaker to slow down the vehicle. If the speed is within the safe range, the roadbreaker remains flat.

A **16x2 LCD display with I2C** provides real-time system feedback such as:
- system mode
- measured speed
- safety messages
- alert conditions

An **ESP32 microcontroller** is integrated to provide wireless communication. When overspeeding is detected, the ESP32 sends an alert to a mobile device through Wi-Fi. The proposal identifies the major system elements as follows: inputs are the two IR sensors and the Grove Light Sensor; controllers are the Arduino Uno and ESP32; outputs are the servo motor, LCD display, and phone alert system.

---

# III. MATERIALS AND COMPONENTS USED

## A. Materials
1. Black foam board  
2. Styro foam  
3. Colored paper  
4. Electrical tape  
5. Corrugated plastic  
6. Small wood  
7. Black acrylic  
8. Glue gun and glue stick  
9. Artificial grass  
10. Small toy car  
11. Sticks (for the post of light)  
12. Phone (for alerts)  
13. Soldering iron  
14. Soldering lead  
15. Wire cutter  
16. Acrylic paint (black and yellow)  
17. Paintbrush  
18. Adhesive tapes (foam, nano, and double-sided)  

## B. Electronic Components
1. 1 × Arduino Uno Microcontroller  
2. 1 × 30-pin ESP32 Microcontroller  
3. 2 × IR Sensors  
4. 1 × Grove Light Sensor  
5. 5 × LEDs  
6. 1 × Servo Motor  
7. 1 × 16x2 LCD Display with I2C  
8. 2 × 18650 3.7V Batteries  
9. 1 × 18650 (2 Cell Battery Holder)  
10. 2 × Breadboards  
11. 1 × LM2596S DC-DC Buck Converter  
12. 1 × Rocker Switch  
13. 1 × 4-Channel Bi-Directional Logic Converter  
14. 5 × 220 Ohm Resistors  
15. Solid wires  
16. Jumper wires  

---

# IV. PERSPECTIVE (PICTURES)
| ISOMETRIC VIEW |
|----------|
| <img width="430" height="300" alt="IMG_3439" src="https://github.com/user-attachments/assets/4a99e34e-4747-444b-ae14-bed43c58871d" />|

| TOP VIEW | BACK VIEW |
|----------|------------|
|<img width="200" height="150" alt="IMG_3444" src="https://github.com/user-attachments/assets/14e1362a-0820-4495-9af8-35f697f48db5" /> |<img width="200" height="150" alt="IMG_3447" src="https://github.com/user-attachments/assets/46b16103-661b-437f-b3a4-b5996461d70b" />|

 | SIDE VIEW | FRONT VIEW |
 |----------|----------------|
 |<img width="200" height="150" alt="image" src="https://github.com/user-attachments/assets/be691359-acb6-4926-a38d-87227ade735a" /> |<img width="200" height="150" alt="IMG_3443" src="https://github.com/user-attachments/assets/24e85bc1-4662-49b0-b152-6e321c5f4b36" />|


# V. PROCEDURE

## A. Planning and Design
1. Identified overspeeding as a road safety problem that can be addressed using automation and embedded systems.  
2. Designed the overall system architecture including sensing, actuation, display, and alert transmission.  
3. Prepared the block diagram, selected the necessary materials and components, and planned the prototype layout.  

## B. Fabrication of the Prototype
1. Constructed the road model using black foam board, styro foam, corrugated plastic, colored paper, black acrylic, and small wood.  
2. Applied paint and finishing details to represent actual road markings and boundaries.  
3. Added artificial grass, toy car, and support structures for improved visual presentation.  
4. Built the roadbreaker portion and allocated a movable section for servo-controlled elevation.  

## C. Circuit Assembly
1. Mounted the Arduino Uno, ESP32, breadboards, buck converter, and rocker switch.  
2. Installed and aligned the two IR sensors for speed measurement.  
3. Connected the Grove Light Sensor for ambient light detection.  
4. Connected the five LEDs with resistors as indicator outputs.  
5. Connected the 16x2 LCD with I2C for real-time feedback.  
6. Connected the servo motor to the roadbreaker mechanism.  
7. Connected the 4-channel bi-directional logic converter for safe communication between the Arduino Uno and ESP32.  
8. Integrated the battery holder, 18650 batteries, and LM2596S buck converter for regulated system power.  

## D. Programming
1. Programmed the Arduino Uno to:  
   - read the IR sensors  
   - compute speed  
   - detect day/night mode  
   - update the LCD  
   - control the servo motor  
   - transmit alert data to the ESP32  

2. Programmed the ESP32 to:  
   - connect to Wi-Fi  
   - receive alert information from the Arduino Uno  
   - send mobile notifications  

## E. Testing and Calibration
1. Tested the IR sensors using a toy car to simulate vehicle motion.  
2. Adjusted the spacing and alignment of the IR sensors for reliable detection.  
3. Calibrated the speed thresholds for day and night operation.  
4. Adjusted the servo positions for flat and elevated roadbreaker states.  
5. Verified the LCD display messages and mobile notification behavior.  
6. Repeated trials under different ambient light conditions to confirm adaptive operation.  

---

# VI. RESULTS AND DISCUSSION

The S.A.F.E.R System successfully demonstrated the intended functions of the prototype.

## Results
- The two IR sensors successfully detected the movement of the toy car and enabled speed computation.  
- The Grove Light Sensor successfully identified changes in ambient brightness and allowed adaptive day/night mode selection.  
- The Arduino Uno successfully processed sensor inputs and controlled the LCD, LEDs, and servo motor.  
- The servo motor elevated the roadbreaker when the detected speed exceeded the threshold.  
- The LCD displayed system mode, speed readings, and alert messages in real time.  
- The ESP32 enabled remote alert transmission through Wi-Fi to a mobile device.  

## Discussion
The prototype shows how embedded systems can be applied in an intelligent traffic safety concept. Instead of keeping the roadbreaker permanently raised, the S.A.F.E.R System introduces selective activation, making the concept more adaptive and practical.  

The integration of ambient light detection is also significant because it allows the system to change its operating threshold depending on day or night conditions. This adds a layer of realism and adaptability to the road safety model.  

The division of tasks between Arduino Uno and ESP32 is another strength of the project. The Arduino Uno handles sensing, processing, display, and actuation, while the ESP32 manages wireless communication. This separation improves modularity and system organization.  

## Limitations
- Speed accuracy depends heavily on proper IR sensor alignment and fixed distance measurement.  
- The light sensor threshold may need recalibration in different environments.  
- Alert delivery depends on available Wi-Fi or network connectivity.  
- The prototype is designed for demonstration purposes and would require further engineering development for real-world road deployment.  

---

# VII. REFLECTION / LEARNING SUMMARY

This project provided important learning in both technical and practical areas of engineering.

## Technical Learnings
- Interfacing multiple sensors with a microcontroller  
- Calculating speed using timing-based measurement  
- Implementing adaptive decision logic using ambient light  
- Controlling mechanical movement with a servo motor  
- Displaying real-time data on an LCD with I2C  
- Establishing serial communication between Arduino Uno and ESP32  
- Using Wi-Fi communication for remote alerts  
- Managing portable power supplies using batteries, converters, and switching  

## Practical Learnings
- Organizing hardware layout for cleaner wiring  
- Troubleshooting sensor, power, and communication issues  
- Calibrating thresholds and servo positions  
- Testing and refining a prototype iteratively  
- Combining structural fabrication and electronics into a complete working model  

## Reflection
The S.A.F.E.R System showed how a concept can evolve from a proposal into a working prototype through repeated testing, debugging, and improvement. It strengthened understanding of embedded systems, automation, and communication, while also emphasizing the importance of patience, system organization, and proper calibration during project development.  

---

# VIII. APPENDIX

## A. Block Diagram
| BLOCK DIAGRAM OF A SAFER SYSTEM |
|---------------------------------|
|<img width="400" height="402" alt="image" src="https://github.com/user-attachments/assets/da045791-a0c5-4871-990b-e6ef85b39b84" />|

## B. Wiring
| WIRING OF A SAFER SYSTEM |
|--------------------------|
|<img width="400" height="300" alt="IMG_3458" src="https://github.com/user-attachments/assets/c78a7867-87f5-4c07-8bc8-b84a000a1b4b" />|

| WIRING DIAGRAM OF A SAFER SYSTEM |
|--------------------------|
|<img width="400" height="360" alt="image" src="https://github.com/user-attachments/assets/1df1e172-35e8-46e4-a1df-9d9a011f99f8" />|

## C. Program/Codes
| ARDUINO CODES |
|---------------------------------|
|<img width="929" height="683" alt="image" src="https://github.com/user-attachments/assets/86f72307-7bba-4f15-b2cd-e23318a9b42e" />
<img width="929" height="652" alt="image" src="https://github.com/user-attachments/assets/6a952d5f-715a-4d07-a434-1134ca0327dc" />
<img width="918" height="686" alt="image" src="https://github.com/user-attachments/assets/e2dfa80f-77cb-4fe6-9eab-698dbd715b81" />
<img width="937" height="682" alt="image" src="https://github.com/user-attachments/assets/7f683aaa-b1bd-448d-84ed-8dab6f3b12f0" />
<img width="943" height="676" alt="image" src="https://github.com/user-attachments/assets/5d4a5fc8-e5ce-462c-b35f-9aaf19195365" />
<img width="942" height="653" alt="image" src="https://github.com/user-attachments/assets/e0dbd27f-1395-4a38-83a2-c5ecab5c1ecd" />
<img width="940" height="682" alt="image" src="https://github.com/user-attachments/assets/f3c2cc35-9beb-40e4-a609-f0c75d94e86a" />
<img width="925" height="620" alt="image" src="https://github.com/user-attachments/assets/5c75b09e-c733-4916-b35d-e59eccca4599" />



|

| ESP32 CODES |
|---------------------------------|
|<img width="1013" height="713" alt="image" src="https://github.com/user-attachments/assets/27a1ae3c-10b2-44ca-a4ba-0e6f6fc4613d" />
<img width="931" height="652" alt="image" src="https://github.com/user-attachments/assets/79d922d3-89d6-4fa9-98b8-93d3040d5b47" />
<img width="825" height="679" alt="image" src="https://github.com/user-attachments/assets/e2486110-82c8-4c38-ad40-e0d87b08ea0f" />
<img width="933" height="686" alt="image" src="https://github.com/user-attachments/assets/825938b8-e34a-4a5a-90e9-b95f425b1f1c" />
<img width="939" height="654" alt="image" src="https://github.com/user-attachments/assets/f32f6da4-668b-48bd-86bd-6f11a846467c" />
<img width="935" height="680" alt="image" src="https://github.com/user-attachments/assets/60defbe8-30db-443b-874f-88f7689d539c" />
<img width="923" height="624" alt="image" src="https://github.com/user-attachments/assets/51a5a492-9575-4edd-9321-544dc288e9e4" />
<img width="939" height="510" alt="image" src="https://github.com/user-attachments/assets/41801975-dfe6-4378-b1ec-ea67300463c4" />|






