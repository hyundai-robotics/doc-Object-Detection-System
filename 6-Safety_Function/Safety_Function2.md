# Object Detection System

## 6.2 Safety Function: Approach Detection

When executing the approach detection function, the system operates as follows:【187†source】  
- **If object movement is detected in the detection area**: Outputs a signal inducing the robot to decelerate or stop.  
- **If no object movement is detected in the detection area**:  
  - If the robot is operating, it maintains the current state.  
  - If the robot is stopped, the restart prevention function is activated until a restart signal is received.  

If an object is detected in the **warning zone** of the detection area, the system outputs a robot speed‑reduction guidance signal. If an object is detected in the **stop zone**, the system outputs a robot stop guidance signal. The system’s outputs are transmitted to the robot’s safety‑related main control system, which controls the robot according to the received signals. The safety‑related main control system of the robot periodically transmits robot state information back to the system. The system check...
