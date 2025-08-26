# Object Detection System

## 6.3 Safety Function: Restart Prevention

The restart prevention function prevents an unexpected restart of the robot when movement is detected in the stop zone of the detection area and a robot stop guidance signal has been issued. It periodically receives signals regarding the robot’s state from the robot’s safety‑related main control system to determine whether a restart is allowed. If the current system state is **stopped** and a restart signal is received from the robot’s safety‑related main control system, the system restarts. If the current...
