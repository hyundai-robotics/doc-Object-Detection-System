# Object Detection System

## 4.5 Control Unit

### 4.5.1 Functions

The control unit performs the following functions:  

- Requests all connected sensors to measure object movement  
- Collects signal information measured by all connected sensors  
- Converts the measured values into usable data  
- Determines which area the converted values belong to  
- Outputs a speed control signal if an object is detected in the warning zone  
- Outputs a stop signal if an object is detected in the stop zone  
- Performs self-diagnosis, and if a fault is detected, switches the system to a safe state  
- Maintains the safe state until a signal is received from the robot’s safety-related main control system when the robot is stopped  
- Manages system input/output using feedback values  
