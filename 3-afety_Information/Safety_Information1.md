# Object Detection System

## 3.1 Purpose

The appropriate operating scenarios for the object detection system are as follows:  
- Protection of designated area access when used in an attached form on the collaborative robot HDC35-18  
- Indoor and application situations where the system operates in a suitably separated space  

The object detection system detects objects approaching the robot and supports the following safety functions at the level of **SIL 2** (based on IEC 61508:2010) and **PL d** (based on ISO 13849-1:2023):  

- **Object Detection Function**: When one or more objects, including humans, approach the designated area, the system detects it and sends a signal to the robot’s safety-related main control system to induce the robot to stop.  
- **Restart Prevention Function**: If an object is detected in the designated area and the robot stops, unintended restarting of the robot is prevented until a restart signal is received by the robot’s safety-related main control system.  

The safety-related requirements for safety functions that need risk reduction measures are satisfied:  
- SIL 2 based on IEC 61508:2010  
- PL d, category 3 based on ISO 13849-1:2023  

The measurement performance requirements for sensors used in the safety functions are satisfied according to:  
- IEC/TS 61496-5:2023  

![Warning Symbol](../_assets/경고기호.png)

If a failure occurs in any component of the system, the system transitions to a safe state, and the safety-related functions cannot be used. If the user intentionally forces the safety-related functions despite the system being in a safe state, the correct operation of the safety-related functions cannot be guaranteed.  
