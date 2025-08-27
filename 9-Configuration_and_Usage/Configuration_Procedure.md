# Object Detection System

## 9.1 Configuration Procedure

![Warning Symbol](../_assets/경고기호.png)

The system’s initial configuration must only be performed by authorized personnel. Before configuration, it must be verified that the robot controlled by the system operates as intended.

### 9.1.1 System Connection Verification
To verify system connections, check the following using the TP (Teach Pendant):
- Ensure the control unit and all sensor units are properly connected.  
- Verify communication between the control unit and each sensor unit.  
- Confirm that IDs of each sensor unit are set correctly and uniquely.  

### 9.1.2 Detection Area Settings
When setting detection areas, configure the following according to the robot’s working environment:
- Define the robot’s working area, stop zone, and warning zone.  
- Ensure that the detection start distance is set outside of the robot’s operating range.  
- Configure angles and distances in accordance with the installation environment.  

### 9.1.3 Safety Function Verification
After configuration, verify that the following safety functions operate properly:

**Approach Detection Function**  
- *Condition*: Move a test object into the detection area.  
- *Test*: Confirm that the system outputs a deceleration or stop signal.  
- *Expected Result*: The robot responds by decelerating or stopping.  

**Restart Prevention Function**  
- *Condition*: With the robot stopped, place an object in the stop zone.  
- *Test*: Attempt to restart the robot.  
- *Expected Result*: The robot must not restart until the stop zone is clear and a restart signal is issued.  

### 9.1.4 Verification of Additional Functions

**Axis Rotation Prevention Function**  
- *Condition*: Rotate the sensor around its axis.  
- *Test*: Confirm that the system issues a warning.  
- *Expected Result*: A warning is displayed and logged.  

**Sensor Front Obstruction Detection Function**  
- *Condition*: Place an obstacle in front of the sensor.  
- *Test*: Confirm that the system detects the obstruction.  
- *Expected Result*: A warning is issued if the obstruction persists.  
