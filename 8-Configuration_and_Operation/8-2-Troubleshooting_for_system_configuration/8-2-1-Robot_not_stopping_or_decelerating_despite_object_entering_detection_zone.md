### 8.2.1	Robot not stopping or decelerating despite object entering detection zone
 This issue is generally caused by the following factors:
-	The radar replan function is not activated
-	Presence of obstacles that obstruct detection within the sensor’s measurement range
-	An object enters from the sensor’s blind spot
-	The radar object detection parameters are incorrectly configured
-	Detection zones (zone1 ~ zone4) are incorrectly configured

Issues caused by the above factors can be resolved through the following methods:
-	Activate the radar replan function
-	Remove any obstacles that could interfere with detection, if possible
-	Establish additional safety measures to resolve undetected objects that may occur in blind spots
-	Set the radar object detection parameters suitable for the operating environment
-	Configure the detection zones (zone1 ~ zone4) suitable for the operating environment
-	Minimize conductive or metallic objects
