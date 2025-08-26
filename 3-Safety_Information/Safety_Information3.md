# Object Detection System

## 3.3.1 General Warnings
- Proper operation of the system assumes that installation and configuration work has been performed correctly. If installation and configuration are not carried out properly, the performance of safety functions may be degraded or may not operate at all.  
- If the system configuration is arbitrarily changed, the performance of safety functions may be degraded or may not operate. When changing the configuration, it must be verified that the system operates correctly.  
- If static objects or metallic objects exist within the detection area, detection performance may be degraded or objects may not be detected. Placement of objects that can cause performance degradation within the detection area should be minimized, and if unavoidable, additional safety measures (e.g., fencing) are recommended.  
- It must be ensured that the storage or installation location temperature complies with the temperature range specified in this document. If stored or installed at excessively low or high temperatures, the performance of the system may be degraded or it may not operate.  

## 3.3.2 Warnings Regarding Object Detection Function
- The object detection function is not guaranteed if an object approaches from blind spots where the sensor cannot measure. If safety requirements are derived from risk assessment at the robot level for objects approaching from blind spots, separate safety measures must be implemented.  
- The object detection function must only be activated in a safe state. If a person has entered the robot's working or stop area before system activation, operational safety cannot be guaranteed.  
- From the moment the system is activated, the environment within the detection area must not change. If the detection area environment differs from the initial activation state, the system must be restarted or the environment restored to its initial state.  

## 3.3.3 Warnings Regarding Restart Prevention Function
- The restart prevention function is not guaranteed if an object is located in blind spots where the sensor cannot measure. If safety requirements are derived from risk assessment at the robot level for objects located in blind spots, separate safety measures must be implemented.  
- The restart signal cannot be arbitrarily provided by the user. Only the robot’s safety-related main control system can provide the activation signal. If arbitrarily modified, the performance of the safety functions may be degraded or may not operate.  

## 3.3.4 Warnings Regarding Improper Use

![Warning Symbol](../_assets/경고기호.png)

Improper use includes arbitrary technical/electrical modifications, replacements, damage, or removal of the product or its components. Using the product for purposes other than those specified in this document also constitutes improper use. Additionally, using the product beyond its specifications, parameters, or characteristics is considered improper use. Improper use of the product may cause performance degradation and malfunction, and the safety functions of the product cannot be guaranteed.  

## 3.3.5 Warnings Regarding EMC

![Caution Symbol](../_assets/느낌표기호.png)

The system described in this document is designed for use in industrial environments. If used in non-industrial environments, measures must be taken to comply with EMC standards and guidelines applicable to that environment.  

## 3.3.6 Responsibility
The product manufacturer and designer are responsible for the following operations:  
- Proper integration of input/output between the object detection system and the robot’s safety-related main control system  
- Verification and confirmation of the system monitoring area  
- Compliance with the contents of this document  

## 3.3.7 Limitations
- If an object is located within the robot's operating range, it cannot be detected by the sensor. If the object is stationary or metallic, it may not be detected by the sensor. For humans, if the person is not breathing or their upper body is not within the sensor's measurement range, they may not be detected.  
- Objects falling from above the robot or protruding from the robot cannot be detected.  
- The system must be electronically controlled.  
- The integrated control system of the robot and the system described in this document must operate within 30 meters of each other.  
