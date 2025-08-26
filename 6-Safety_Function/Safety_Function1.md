# Object Detection System

## 6.1 Overview of Safety Functions

The system performs the following safety functions:【186†source】
- **Approach Detection**: If an object is detected within the detection area, the system transitions to a safe state.  
- **Restart Prevention**: Prevents unexpected restart of the robot, maintaining a safe state.  

Each safety function satisfies SIL 2 of IEC 61508:2010 and PL d of ISO 13849‑1:2023. Both safety functions do not directly control the robot. Instead, the safety‑related main control system of the robot receives the guidance signals output from the system, controls the robot accordingly, and returns feedback to the system. Through the received feedback, the system verifies whether the safety function has operated correctly. If the output guidance signal and the feedback result do not match, the system swi...
