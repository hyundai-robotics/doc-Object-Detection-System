## 4.4	Control unit functions
The control unit performs the following functions:
-	Requests object movement measurement from all connected sensor units
-	Collects measured data from all connected sensor units
-	Converts the measured values into applicable data
-	Determines which zone the converted measured values belong to
-	Outputs a robot stop signal if an object is present in the stop zone
-	Outputs a robot deceleration signal if an object is present in the warning zone
-	Performs self-diagnosis and transitions the system to a safe state if a fault is detected
-	Maintains the state after robot stop or deceleration due to object detection until a restart signal is received from the main controller
-	Manages system inputs and outputs using feedback values
