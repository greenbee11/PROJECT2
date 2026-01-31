# PROJECT2
Team Members: Iyene Essien & Eric Greenberg

System Behavior: 
---------------------------------------------------------------------------------------------------------------------------
This project implements an enhanced vehicle safety and lighting control system using an ESP32-S3 microcontroller. 
The system check the following:
- if the driver and passenger seats are occupied 
- if the driver and passenger seatbelts are on

The system also has an ignition button that needs to be pressed before allowing the engine to start and provides LED and buzzer feedback if conditions are unsafe.

 After ignition has been started and the engine is running, the system controls headlights using OFF, ON, or AUTO modes. For the AUTO mode, the system uses a light sensor with delays. The system also has a switch that allows manual high-beam control when the headlights are on.



Starting Repository: 
---------------------------------------------------------------------------------------------------------------------------
This project builds on the structure and concepts developed in Project 1 of Iyene's code. The original repository included basic GPIO input and output handling using ESP-IDF. Project 2 expands on this by adding ADC-based sensing, timing logic, and multi-condition decision making. 

Summary of Testing Results:
---------------------------------------------------------------------------------------------------------------------------

### Subsystem 1: Safety & Ignition Control

Note: "Pass" means that the system worked as expected
| Behavior | Test Process | Result |
| --- | --- | --- |
Driver seat detection         | Toggled driver seat input via button and observed serial output      |           Pass
Passenger seat detection      | Toggled passenger seat input via button and observed system response |           Pass
Driver seatbelt detection     | Simulated belt fastened and unfastened states via button            |           Pass
Passenger seatbelt detection  | Simulated belt fastened and unfastened states via button            |           Pass
Ready-to-start indication     | Checked green LED when all safety conditions were met     |           Pass
Ignition inhibited when unsafe| Pressed ignition button with missing safety conditions    |           Pass
Error message when unsafe     | Read terminal after pressing any combination of buttons plus ignition | Pass
Engine start when safe        | Pressed ignition button with all conditions met           |           Pass
Engine-on indication          | Checked red and green LEDs when ignition button pressed   | Pass
Engine stop                   | Pressed ignition button while engine was running          |           Pass



### Subsystem 2: Lighting Control
Behavior                      |                      Test Process                         |          Result
| --- | --- | ---
Headlights OFF mode           | Set mode selector to OFF and observed low beams           |           Pass
Headlights ON mode            | Set mode selector to ON and observed low beams            |           Pass
AUTO mode (dark)              | Reduced light sensor input to simulate darkness           |           Pass
AUTO mode (bright)            | Increased light sensor input to simulate daylight         |           Pass
AUTO mode delay behavior      | Rapidly changed light levels                              |           Pass
High-beam activation          | Pressed high-beam switch with headlights on               |           Pass
High-beam inhibited           | Pressed high-beam switch with headlights off              |           Pass
