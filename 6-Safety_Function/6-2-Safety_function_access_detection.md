## 6.2	Safety function: access detection
When performing the access detection function, the system operates as follows:
-	When object movement is detected in the detection area: The system outputs a signal to either reduce the robot’s speed or induce a stop.
-	When no object movement is detected in the detection area: Maintain current robot status.

If an object is detected in the stop zone, the system outputs a robot stop signal. If an object is detected in the warning zone, the system outputs a robot deceleration signal. These system outputs are transmitted to the robot's safety-related main control system, which controls the robot according to the received signals.
