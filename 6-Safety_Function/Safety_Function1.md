# Object Detection System

## 6.1 Overview of Safety Functions

The system performs the following safety functions:【186†source】
- **Approach Detection**: If an object is detected within the detection area, the system transitions to a safe state.  
- **Restart Prevention**: Prevents unexpected restart of the robot, maintaining a safe state.  

Each safety function satisfies SIL 2 of IEC 61508:2010 and PL d of ISO 13849-1:2023.
Neither of the two safety functions directly controls the robot.
The guidance signals output from the system are received by the robot’s safety-related main control system, which then controls the robot and sends the results back to the system as feedback.
Using the received feedback, the system verifies whether the safety functions have operated correctly.
If the output guidance signal and the feedback result do not match, the system switches to a safe state.
