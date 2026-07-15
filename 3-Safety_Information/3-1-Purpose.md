##  3.1	Purpose
The appropriate operating scenarios for the object detection system are as follows:
-	Designed for installation and use with the HDC series
-	An indoor environment where a risk assessment has been completed

The object detection system detects approaching objects and supports the following safety functions at the SIL 2 level based on IEC 61508:2010 and the PL d level based on ISO 13849-1:2023:
-	Object Detection Function: When an object approaches the designated zone, the system detects it and transmits a signal to the main controller to initiate a robot stop or deceleration.
-	Restart Prevention Function: When an object is detected in the designated area and the robot is stopped or decelerated, this system prevents the unintended restart of the robot until a restart signal is received from the main controller.

The system satisfies the safety-related requirements for safety functions requiring risk reduction measures:
-	SIL 2 according to IEC 61508:2010
-	PL d, Category 3 according to ISO 13849-1:2023

The measurement performance of the sensors used for safety functions meets the following performance requirements:
-	IEC/TS 61496-5:2023

{% hint style="danger" %}
In the event of a failure occurring in any component of the system, the system will transition to a safe state, and the safety-related functions will become unavailable. If the user intentionally attempts to operate the safety-related functions after the system has transitioned to the safe state, the correct operation of the safety-related functions cannot be guaranteed.
{% endhint %}
