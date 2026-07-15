### 8.2.2	Robot not operating normally despite detection target moving outside detection zone
 This issue is generally caused by the following factors:
-	Presence of moving objects within the sensor’s measurement range (including the robot arm)
-	Vibration or movement of the sensor occurs
-	The sensor detects a non-existent object

Issues caused by the above factors can be resolved through the following methods:
-	Remove all other moving objects within the sensor's detection zone, except for the detection target
-	Modify the sensor's detection zone so that no other moving objects exist within it, except for the detection target
-	Configure the environment to prevent sensor vibration or movement
-	Modify the radar object detection parameters to prevent the detection of non-existent objects
-	Minimize conductive or metallic objects
