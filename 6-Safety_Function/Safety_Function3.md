# Object Detection System

## 6.3 Safety Function: Restart Prevention

The restart prevention function prevents the robot from restarting unexpectedly when movement is detected in the stop zone of the detection area and a robot stop guidance signal has been issued.
It periodically receives signals regarding the robot’s status from the robot’s safety-related main control system to determine whether a restart is permitted.
If the current system state is stopped and a restart signal is received from the robot’s safety-related main control system, the system restarts.
If the current system state is not stopped or no restart signal is received from the robot’s safety-related main control system, the current state is maintained
