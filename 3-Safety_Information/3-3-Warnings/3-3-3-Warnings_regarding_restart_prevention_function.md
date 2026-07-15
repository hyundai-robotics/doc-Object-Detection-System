### 3.3.3	Warnings regarding restart prevention function
-	The restart prevention function cannot be guaranteed if an object is located in a blind spot where the sensor cannot measure. If a robot-level risk assessment identifies safety requirements for objects in blind spots, additional safety measures must be implemented.
-	The restart signal must be transmitted only through the main controller, and the user cannot arbitrarily assign this signal. Unauthorized modification of the system may degrade safety functions or cause them to malfunction.
