## 6.1	Overview
The system performs the following safety functions:
-	Approach Detection: Transitions the system to a safe state when an object is detected within the detection area.
-	Restart Prevention: Maintains a safe state by preventing unintended restart of the robot.

Each safety function complies with SIL 2 according to IEC 61508:2010 and PL d according to ISO 13849-1:2023. Both safety functions do not directly control the robot. Instead, the system outputs an induced signal that is received by the robot's main control system, which then controls the robot accordingly. The result is feedback to the system. The system verifies the correct operation of the safety functions based on the received feedback. If the induced signal output by the system and the received feedback do not match, the system transitions to a safe state.
