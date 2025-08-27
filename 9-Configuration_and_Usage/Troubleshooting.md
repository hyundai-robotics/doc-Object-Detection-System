# Object Detection System

## 9.2 Troubleshooting Configuration Issues

This section describes general methods to resolve issues discovered during the verification of safety functions. Problems caused by the environmental characteristics of the system’s operating environment may not be fully resolved.

### 9.2.1 Robot Does Not Slow Down or Stop Even When a Target Enters the Detection Area

This issue generally occurs due to the following causes:
* An obstacle exists within the sensor’s measurement range that interferes with detection.  
* The installation height of the sensor is too low or too high.  
* The measurement distance/sensitivity of the sensor is too low.  
* The configured distance of the system’s warning/stop zone is incorrect.  

Problems arising from the above causes can be resolved as follows:
* Remove any obstacles that may interfere with detection, if possible.  
* If removing the obstacle is not possible, implement additional safety measures in the affected area.  
* Modify the sensor’s measurement distance/sensitivity configured in the system to suit the environment.  
* Adjust the system’s configured warning/stop zone distance to suit the environment.  

### 9.2.2 Robot Does Not Operate Even When the Target Has Moved Out of the Detection Area

This issue generally occurs due to the following causes:
* An obstacle exists within the sensor’s measurement range that interferes with detection.  
* A moving object exists within the sensor’s measurement range (including the robot arm).  
* Vibration occurs in the robot on which the sensor is mounted.  
* Signal reflection occurs due to environmental characteristics.  

Problems arising from the above causes can be resolved as follows:
* Remove any obstacles that may interfere with detection, if possible.  
* Reconfigure the robot’s working area so that the robot arm does not enter the detection area.  
* Adjust the coupling between the robot and the sensor to minimize vibration transmission.  
* Adjust the sensor’s sensitivity so that reflected measurement values are not recognized.  
* Modify the detection area to ensure reflective objects are not included within the detection area.  
