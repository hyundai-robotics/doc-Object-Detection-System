# Object Detection System

## 4.1 System Description

### 4.1.1 System Definition
The object detection system actively monitors the working area of a collaborative robot. When the approach of an object within a distance that may cause danger is detected, the system induces the robot to stop to prevent accidents.

The object detection system consists of one control unit and up to four sensor units. The sensor units and the control unit are connected using CAN communication. The sensor units connected to a single control unit have different node IDs depending on their position. The user can modify the system parameters using the Teach Pendant (TP).

### 4.1.2 System Functions
- Detect the current distance between the object detected by the sensor and the robot  
- Adjust the detection area to apply to various environments  
- Connect up to four sensor units  
- Set individual detection areas and sensitivity for each sensor unit  
- Prevent false detections during operation by storing the initial installation angle of the sensor unit  
- Adjust sensor sensitivity according to configuration and environment  
