
[__SOURCE](0-about-this-manual/README.md)
# About the Manual

[__SOURCE](0-about-this-manual/precautions.md)
# Precautions

{% include file="en/precautions.md" %}

[__SOURCE](0-about-this-manual/safety-notice.md)
# Safety Cautions

{% include file="en/safety-notice.md" %}

[__SOURCE](1-Overview/README.md)
# 1	Overview
[__SOURCE](1-Overview/1-1-Purpose_of_the_document.md)
## 1.1	Purpose of the document
This document describes the object detection system, a subsystem installed on the HDC series (HDC25-18, HDC35-18, HDC50-17). This manual provides safety regulations to ensure the safety of operators controlling and operating the system, and specifies guidelines required for proper installation, operation, and maintenance.<br>
This document includes safety-related information based on IEC 61508. All safety-related elements are based on the assumption that the system operates as a subsystem of the HDC series. Operating the object detection system standalone does not guarantee safety.<br>
This document does not address the HDC series itself, the robot’s main safety control system, or any peripheral devices.

[__SOURCE](1-Overview/1-2-Related_obligations.md)
## 1.2	Related obligations
This document constitutes a major component of the product and must be retained for the entire useful life of the product. It must be referenced in all situations involving the object detection system, from the time of delivery until disposal. The document must be stored in an easily accessible location, protected from damage, and where there is no risk of deterioration. If the document is lost or damaged, the user must contact the supplier for a replacement.


[__SOURCE](1-Overview/1-3-Target_users.md)
## 1.3	Target users
-   **Manufacturer**: The company that developed the system
-   **Installer**: Personnel responsible for installing and configuring the system
-   **Maintenance Personnel**: Personnel responsible for maintaining the system


[__SOURCE](2-Terms_and_Abbreviations/README.md)
# 2	Terms and Abbreviations
[__SOURCE](2-Terms_and_Abbreviations/2-1-Terms.md)
## 2.1	Terms
|Term|Description|
|:--|:--|
|Stop zone|A zone where the robot's operation is halted by a stop signal emitted from the object detection system when an object enters the stop area|
|Warning zone|A zone where the robot's speed is reduced by a deceleration signal emitted from the object detection system when an object enters the warning area|
|Robot’s operating range|The area where the robot physically moves and performs its tasks|

[__SOURCE](2-Terms_and_Abbreviations/2-2-Abbreviations.md)
## 2.2	Abbreviations
|Abbreviation|Description|
|:--|:--|
|SIL|Safety Integrity Level|
|PL|Performance Level|
|EMC|Electromagnetic Compatibility|
|CAN|Controller Area Network|
|ID|Identification|
|TP|Teach Pendant|
|CAN-FD|Controller Area Network Flexible Data-rate|
|EtherCAT|Ethernet for Control Automation Technology|
|FSoE|Function Safety over EtherCAT|
|FMCW|Frequency Modulated Continuous Wave|
|RAM|Random Access Memory|
|CPU|Central Processing Unit|
|FPU|Floating Point Unit|
|VCRC|Variable Cyclic Redundancy Check|
|CRC|Cyclic Redundancy Check|

[__SOURCE](3-Safety_Information/README.md)
# 3	Safety Information
[__SOURCE](3-Safety_Information/3-1-Purpose.md)
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

[__SOURCE](3-Safety_Information/3-2-Evaluation.md)
## 3.2	Evaluation
Before using a robot equipped with the system described in this document, a safety assessment in accordance with the Machinery Directive must be conducted. Although the system meets functional safety requirements and has been certified, this does not guarantee the overall safety of the complete robotic system. A separate evaluation must be performed for the safety functions required at the entire robot system level.

{% hint style="danger" %}
After configuring the detection zone and object detection parameters, a safety assessment must be performed.
{% endhint %}

[__SOURCE](3-Safety_Information/3-3-Warnings/README.md)
## 3.3	Warnings
[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-1-General_warnings.md)
### 3.3.1	General warnings
-	Normal operation of the system assumes that installation and configuration tasks have been performed correctly. If the installation and configuration are not performed properly, the performance of the safety functions may be degraded, or the safety functions may fail to operate normally.
-	If the system configuration is modified arbitrarily, the performance of the safety functions may be degraded, or the safety functions may fail to operate normally. If the system configuration is changed, it must be verified that the system operates correctly.
-	When operating or storing the system, it must be verified that the environmental specifications (temperature, humidity, etc.) stated in this document are met. Operating or storing the system in environments outside the allowable range may cause performance degradation or malfunctions.

[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-2-Warnings_regarding_object_detection_function.md)
### 3.3.2	Warnings regarding object detection function
-	The object detection function cannot be guaranteed if an object approaches from a blind spot where the sensor cannot measure. If the risk assessment at the robot system level identifies safety requirements for objects approaching from blind spots, separate safety measures must be implemented.
-	Before activating the object detection function, it must be verified that all zones (warning zone, stop zone) are clear of objects. If the function is activated while an object is present within these zones, safety cannot be guaranteed.
-	If static objects or conductive/metallic objects are present within the detection zone, detection performance may degrade, or false detections and missed detections may occur. Objects that can cause performance degradation within the sensor’s detection zone must be minimized. If such objects must be deployed inevitably, additional safety measures (e.g., installing fences) must be implemented.
-	The environment within the detection zone must remain unchanged after system activation. Any deviation from the initial environment may degrade performance, causing false or missed detections. If the environment changes, it must be restored to its original state, or the system must be reconfigured and reset to match the new environment.

[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-3-Warnings_regarding_restart_prevention_function.md)
### 3.3.3	Warnings regarding restart prevention function
-	The restart prevention function cannot be guaranteed if an object is located in a blind spot where the sensor cannot measure. If a robot-level risk assessment identifies safety requirements for objects in blind spots, additional safety measures must be implemented.
-	The restart signal must be transmitted only through the main controller, and the user cannot arbitrarily assign this signal. Unauthorized modification of the system may degrade safety functions or cause them to malfunction.

[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-4-Warning_regarding_improper_use.md)
### 3.3.4	Warning regarding improper use
{% hint style="danger" %}
Technical or electrical modifications, replacements, damage, or removal of the product or its components constitute improper use. Using the product for purposes other than those specified in this document also constitutes improper use. Furthermore, using the product beyond its defined specifications, parameters, or characteristics constitutes improper use. In the event of improper use, the functionality of the product, including its safety functions, cannot be guaranteed. Improper use may result in performance degradation or malfunction.
{% endhint %}

[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-5-Warning_regarding_EMC.md)
### 3.3.5	Warning regarding EMC
{% hint style="warning" %}
The system described in this document is designed for use in industrial environments. If used in non-industrial environments, appropriate measures must be taken to comply with the applicable EMC standards and guidelines required for that environment.
{% endhint %}

[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-6-Responsibility.md)
### 3.3.6	Responsibility
The product manufacturer and system designer are responsible for the following:
-	Proper integration of input and output between the object detection system and the safety-related main controller
-	Verification and confirmation of the system monitoring areas
-	Compliance with the contents of this document


[__SOURCE](3-Safety_Information/3-3-Warnings/3-3-7-Limitations.md)
### 3.3.7	Limitations
-	Due to the nature of the sensor, stationary or slow-moving objects may not be detected.
-	Since reflectivity varies depending on the object's material and surface area, the sensor's detection performance may significantly degrade if the object is conductive/metallic or if the detection area is insufficient.
-	If the sensor is subjected to vibration, its detection performance may degrade.
-	Objects descending vertically into the detection zone, or unexpected events occurring within the robot’s operating range (e.g., an object detaching from the robot), may not be detected.
-	The system must be electronically controlled.

[__SOURCE](3-Safety_Information/3-4-Standards.md)
## 3.4	Standards
-	ISO 13849-1:2023
-	ISO 13849-2:2016
-	ISO 61508:2010
-	IEC 61496-1:2020
-	IEC 61496-5:2023
-	IEC61000-6-7:2014
-	IEC 61326-3-1:2017
-	IEC 61800-3-2:2017

[__SOURCE](4-System_Information/README.md)
# 4	System Information
[__SOURCE](4-System_Information/4-1-System_description/README.md)
## 4.1	System description
[__SOURCE](4-System_Information/4-1-System_description/4-1-1-System_definition.md)
### 4.1.1	System definition
The object detection system captures object movement within the configured detection zone and transmits a deceleration or stop signal to the robot, thereby preventing potential accidents in advance.<br>
The object detection system consists of one control unit and up to six sensor units. The sensor units and the control unit are connected via CAN FD communication. Each sensor unit connected to a control unit has a unique node ID. Users can modify system parameters using the TP.

[__SOURCE](4-System_Information/4-1-System_description/4-1-2-System_function.md)
### 4.1.2	System function
-	Supports up to 6 sensor units (4 default built-in sensors, up to 2 additional external sensors)
    -   Configurations that decrease the number of built-in sensors to increase the number of external sensors are not allowed. (e.g., A configuration of 3 built-in sensors and 3 external sensors is not permitted)
-	Measurement of distance and angle between the sensor and the object
-	Detection zone configuration for each sensor unit
-	Robot deceleration ratio configuration for each detection zone

[__SOURCE](4-System_Information/4-1-System_description/4-1-3-System_parameters.md)
### 4.1.3	System parameters
System parameters can be modified using the TP. Below are the configurations and default values of the parameters that can be monitored by the user:


<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">Radar sensor setting</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">Parameter</td>
      <td style="text-align: center;">Min.</td>
      <td style="text-align: center;">Max.</td>
      <td style="text-align: center;">Default</td>
      <td style="text-align: center;">Note</td>
    </tr>
    <tr>
      <td>Active</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0 = disable, 1 = enable</td>
    </tr>
    <tr>
      <td>zone1</td>
      <td>500</td>
      <td>5000</td>
      <td>1000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>zone2</td>
      <td>500</td>
      <td>5000</td>
      <td>2000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>500</td>
      <td>5000</td>
      <td>3000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>500</td>
      <td>5000</td>
      <td>4000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>End point</td>
      <td>500</td>
      <td>5000</td>
      <td>5000</td>
      <td>Unit: mm</td>
    </tr>
    <tr>
      <td>Valid azimuth start</td>
      <td>-55</td>
      <td>55</td>
      <td>-55</td>
      <td>Unit: &deg</td>
    </tr>
    <tr>
      <td>Valid azimuth end</td>
      <td>-55</td>
      <td>55</td>
      <td>55</td>
      <td>Unit: &deg</td>
    </tr>
  </tbody>
</table>
<br>

<table>
  <thead>
    <tr>
      <th colspan="5" style="text-align: center">Object detection parameter setting</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">Parameter</td>
      <td style="text-align: center;">Min.</td>
      <td style="text-align: center;">Max.</td>
      <td style="text-align: center;">Default</td>
      <td style="text-align: center;">Note</td>
    </tr>
    <tr>
      <td>epsilon</td>
      <td>1</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
    <tr>
      <td>min point</td>
      <td>1</td>
      <td>10</td>
      <td>4</td>
      <td></td>
    </tr>
    <tr>
      <td>max speed</td>
      <td>0</td>
      <td>140</td>
      <td>140</td>
      <td></td>
    </tr>
    <tr>
      <td>hit active</td>
      <td>1</td>
      <td>50</td>
      <td>1</td>
      <td></td>
    </tr>
    <tr>
      <td>hit stop</td>
      <td>1</td>
      <td>50</td>
      <td>30</td>
      <td></td>
    </tr>
    <tr>
      <td>idis</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td></td>
    </tr>
    <tr>
      <td>tracker radius</td>
      <td>0</td>
      <td>20</td>
      <td>10</td>
      <td></td>
    </tr>
  </tbody>
</table>
<br>

{% hint style="danger" %}
System parameters directly impact detection performance. Therefore, after configuring parameters, it is essential to verify proper functionality and conduct a comprehensive risk assessment.
{% endhint %}

[__SOURCE](4-System_Information/4-2-Communication/README.md)
## 4.2	Communication
[__SOURCE](4-System_Information/4-2-Communication/4-2-1-Sensor_unit-Control_unit_communication.md)
### 4.2.1	Sensor unit – Control unit communication
The sensor units and the control unit communicate using a CAN-FD bus. Communication between the sensor units and the control unit is diagnosed to ensure compliance with SIL 2 and PL d levels. Multiple sensor units connected to a single control unit must have unique IDs. The control unit and each sensor unit communicate using their respective unique IDs. By default, sensor units are assigned IDs based on their installation locations. Of the two IDs assigned to each sensor unit, odd IDs are allocated to Part A, and even IDs are allocated to Part B. The IDs for the built-in sensor units are assigned as shown below. For the setting method when the IDs are 1 and 2, refer to the figure below.

<p align="center">
    <img src="../../_assets/4.2.1_figure_1.png" width="500"> </img>
</p>
[__SOURCE](4-System_Information/4-2-Communication/4-2-2-Control_unit-main_controller_communication.md)
### 4.2.2	Control unit – main controller communication
The control unit and the main controller communicate using FSoE based on EtherCAT. FSoE complies with the IEC 61508 standard and supports up to SIL 3. All safety-related parameters are managed by the main controller, and the control unit receives and uses them as necessary. The TP, which allows users to control parameters, is also connected to the main controller. When the control unit receives safety-related parameters from the main controller, it verifies whether the received values are appropriate to maintain compliance with SIL 2 and PL d levels.

[__SOURCE](4-System_Information/4-3-Sensor_unit_functions.md)
## 4.3	Sensor unit functions
The sensor unit performs the following functions:
-	Detects movement of objects within the configured detection range
-	Sends signals regarding detected object movement to the control unit
-	Performs self-diagnosis to detect faults and transmits fault information to the control unit when a fault is detected

[__SOURCE](4-System_Information/4-4-Control_unit_functions.md)
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

[__SOURCE](5-Operation_Principle/README.md)
# 5	Operation Principle
[__SOURCE](5-Operation_Principle/5-1-Sensor/README.md)
## 5.1	Sensor
[__SOURCE](5-Operation_Principle/5-1-Sensor/5-1-1-Sensor_operating_principle.md)
### 5.1.1	Sensor operating principle
Each sensor unit consists of two independent sensor elements. These sensors are FMCW radar devices that measure the position of moving objects within the detection area by using continuously frequency-modulated signals. A continuous wave emitted from the transmitter collides with an object and is reflected back to the receiver. Since the frequency of the transmitted signal changes continuously over time, a frequency difference occurs when the transmitted and received signals are compared. This frequency difference is then used, through Doppler shift analysis, to calculate the distance to the object.

[__SOURCE](5-Operation_Principle/5-1-Sensor/5-1-2-Factors_affecting_detection_performance.md)
### 5.1.2	Factors affecting detection performance

{% hint style="danger" %}
If a conductive or metallic object is located in front of the sensor, the transmitted signal cannot penetrate it, which may affect object detection performance. If there is a high probability that conductive or metallic objects will be present in the system's operating environment, additional safety measures must be implemented based on a risk assessment.
{% endhint %}
[__SOURCE](5-Operation_Principle/5-1-Sensor/5-1-3-Factors_affecting_reflected_signals.md)
### 5.1.3	Factors affecting reflected signals

{% hint style="danger" %} 
The strength of the reflected signal may vary depending on the characteristics and material of the object. Since this affects system operation, the safety function may be unnecessarily activated due to false positives in actually safe situations. Conversely, it may fail to activate due to false negatives when a stop or deceleration is required. When operating the system, parameters must be configured to optimize detection performance, taking into account reflected signal interference from objects or the surrounding environment.
-	Size: Larger objects reflect stronger signals. Smaller objects are more likely to produce weaker signals.
-	Shape: Smooth surfaces (e.g., metal plates) tend to reflect signals directly or in a focused manner, whereas irregular or rough surfaces scatter signals in various directions, potentially weakening the reflected signal strength.
-	Material: Highly reflective materials such as metals or dense substances generate strong reflected signals. Absorptive materials (e.g., plastics, rubber, and fabrics) can attenuate the signal strength.
-	Speed: If the object moves too fast or too slow, errors may occur in signal analysis.
-	Multipath Effects: Signal reflections from surrounding structures other than the detection target (e.g., walls or floors) may result in unwanted interference signals. 
{% endhint %}

[__SOURCE](5-Operation_Principle/5-1-Sensor/5-1-4-Detectable_and_non-detectable_objects.md)
### 5.1.4	Detectable and non-detectable objects

{% hint style="danger" %} 
Only objects moving at a measurable speed within the detection zone can be detected; detection of stationary objects is not guaranteed.
{% endhint %}

[__SOURCE](5-Operation_Principle/5-2-Detection_area/README.md)
## 5.2	Detection area
[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-1-Meaning_of_detection_area.md)
### 5.2.1	Meaning of detection area
The detection area refers to a designated zone within the sensor’s measurable range, and up to four detection areas can be configured. The detection zone is broadly divided into a stop zone and a warning zone; the stop zone comprises Zone 1, while the warning zone comprises Zones 2 through 4. Even if an object is detected within the sensor's measurable range, the robot will not stop or decelerate if the object is outside the designated detection areas. Each area can be enabled or disabled.


[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-2-Detection_area_parameters.md)
### 5.2.2	Detection area parameters
 The parameters used to define detection areas are as follows:
-	Start Position for each zone
-	End position of the last zone
-	Detection start/end azimuth

[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-3-Stop_area-distance.md)
### 5.2.3	Stop area distance
Zone 1 corresponds to the stop zone; when the radar sensor is activated, Zone 1 is also automatically enabled. The Zone 1 value entered via the TP represents its starting point, whereas its ending point is determined by the starting point of the next active zone. If no other zones are active, the user-defined value is applied as the ending point. Below are examples of the Zone 1 range when the starting point is set to 500:

<table>
  <thead>
    <tr>
      <th style="text-align: center;">Ex.</th>
      <th style="text-align: center;">Parameter</th>
      <th style="text-align: center;">Activation status</th>
      <th style="text-align: center;">Input value</th>
      <th style="text-align: center;">Zone2 range</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>zone2</td>
      <td>enable</td>
      <td>2000</td>
      <td>500 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="vertical-align: middle;">2</td>
      <td>zone2</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="2" style="vertical-align: middle;">500 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>enable</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="4" style="vertical-align: middle;">3</td>
      <td>zone2</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="4" style="vertical-align: middle;">500 ~ 4000 mm</td>
    </tr>
    <tr>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>disable</td>
      <td>-</td>
    </tr>
    <tr>
      <td>End point</td>
      <td>-</td>
      <td>4000</td>
    </tr>
  </tbody>
</table>

[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-4-Warning_area_distance.md)
### 5.2.4	Warning area distance
Zone2 ~ zone4 correspond to the warning zones. The values entered in the TP for these zones represent their respective starting points; the starting point of the next activated zone serves as the end point of the previous zone. For example, when zone2 is activated with its starting point set to 1000 mm, its range is defined as follows:

<table>
  <thead>
    <tr>
      <th style="text-align: center;">Ex.</th>
      <th style="text-align: center;">Parameter</th>
      <th style="text-align: center;">Activation status</th>
      <th style="text-align: center;">Input value</th>
      <th style="text-align: center;">Zone2 range</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>zone3</td>
      <td>enable</td>
      <td>2000</td>
      <td>1000 ~ 2000 mm</td>
    </tr>
    <tr>
      <td rowspan="2" style="vertical-align: middle;">2</td>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="2" style="vertical-align: middle;">1000 ~ 3000 mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>enable</td>
      <td>3000</td>
    </tr>
    <tr>
      <td rowspan="3" style="vertical-align: middle;">3</td>
      <td>zone3</td>
      <td>disable</td>
      <td>-</td>
      <td rowspan="3" style="vertical-align: middle;">1000 ~ 4000 mm</td>
    </tr>
    <tr>
      <td>zone4</td>
      <td>disable</td>
      <td>-</td>
    </tr>
    <tr>
      <td>End point</td>
      <td>-</td>
      <td>4000</td>
    </tr>
  </tbody>
</table>

[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-5-Detection_area_angle.md)
### 5.2.5	Detection area angle
The angle range of the detection zone is between -55° and 55°, and the end azimuth must be greater than the start azimuth. The minimum difference between the start and end azimuths must be at least 15°. If the difference is less than 15°, object detection performance may degrade.

[__SOURCE](5-Operation_Principle/5-2-Detection_area/5-2-6-Calculation_of_the_stop_zone_distance.md)
### 5.2.6	Calculation of the stop zone distance
The system's stop zone corresponds to the hazardous area of the machinery and must be calculated according to the requirements of relevant safety regulations and standards. By default, the stop zone complies with ISO 13855:2010. The user-configured stop zone distance must be greater than or equal to the minimum safety distance required by the standard. The formula for calculating the machinery hazardous area specified in the standard is as follows:

<p align="center">S=K×T+C</p>

-   S: Minimum distance of the stop zone
-   K: Maximum approach speed toward the stop zone
-   T: Time required for the system to stop
-   C: corrective constant according to ISO 13855:2010


The stop zone described in this document has the same meaning as the hazardous area defined in machinery standards. However, the following factors are additionally applied: the radar sensor’s object detection distance error (m) and a user-defined distance (d) based on on-site conditions (e.g., verification results).

<p align="center">S=K×T+C+m+d</p>

-   m: object detection distance error
-   d: user-defined distance


[__SOURCE](6-Safety_Function/README.md)
# 6	Safety Function
[__SOURCE](6-Safety_Function/6-1-Overview.md)
## 6.1	Overview
The system performs the following safety functions:
-	Approach Detection: Transitions the system to a safe state when an object is detected within the detection area.
-	Restart Prevention: Maintains a safe state by preventing unintended restart of the robot.

Each safety function complies with SIL 2 according to IEC 61508:2010 and PL d according to ISO 13849-1:2023. Both safety functions do not directly control the robot. Instead, the system outputs an induced signal that is received by the robot's main control system, which then controls the robot accordingly. The result is feedback to the system. The system verifies the correct operation of the safety functions based on the received feedback. If the induced signal output by the system and the received feedback do not match, the system transitions to a safe state.

[__SOURCE](6-Safety_Function/6-2-Safety_function_access_detection.md)
## 6.2	Safety function: access detection
When performing the access detection function, the system operates as follows:
-	When object movement is detected in the detection area: The system outputs a signal to either reduce the robot’s speed or induce a stop.
-	When no object movement is detected in the detection area: Maintain current robot status.

If an object is detected in the stop zone, the system outputs a robot stop signal. If an object is detected in the warning zone, the system outputs a robot deceleration signal. These system outputs are transmitted to the robot's safety-related main control system, which controls the robot according to the received signals.

[__SOURCE](6-Safety_Function/6-3-Safety_function_Restart_prevention.md)
## 6.3	Safety function: Restart prevention
The restart prevention function is a safety feature that prevents the robot's speed from automatically recovering or the robot from restarting arbitrarily when it has stopped or decelerated due to a detected moving object. The system determines whether to allow a restart by periodically receiving robot status signals from the robot's safety-related main control system. If the system is in a stopped or decelerated state and receives a restart signal from the robot's safety-related main control system, the robot resumes its original speed. If the system is not in a stopped or decelerated state, or if it does not receive a restart signal from the robot's safety-related main control system, it maintains its current state.<br>
The restart signal is generated only when the motor is turned on after releasing the emergency stop switch on the controller.

 
{% hint style="danger" %} 
Always ensure that no operators are inside the radar detection zone before initiating a restart.
{% endhint %}

[__SOURCE](7-Sensor_Usage_and_Installation/README.md)
# 7	Sensor Usage and Installation
When a moving object is detected within the detection zone, the safety function is triggered according to the configuration. This section provides guidelines on sensor positioning and usage methods to ensure the correct operation of the safety function.


[__SOURCE](7-Sensor_Usage_and_Installation/7-1-Situations_requiring_caution.md)
## 7.1	Situations requiring caution
Special attention is required, and additional safety measures may need to be implemented in the following situations:
-	Presence or potential presence of objects within the sensor’s detection area that could obstruct detection
-	An object may approach at a speed exceeding the maximum detectable limit of the sensor
-	There is a risk that an object may approach an area that cannot be detected by the sensor (blind spot).
-	An object may travel in a direction starting from the robot and moving away from it.
 
{% hint style="danger" %} 
Depending on the site environment, ensuring sufficient safety with the radar sensor alone may be difficult. In this case, additional safety devices must be applied.
{% endhint %}

[__SOURCE](7-Sensor_Usage_and_Installation/7-2-Proper_usage_of_built-in_radar_sensor.md)
## 7.2	Proper usage of built-in radar sensor
When using a built-in sensor mounted on the robot base, caution is required as false detections or missed detections may occur if the robot obstructs or passes in front of the sensor. When using only the built-in radar sensors, a terminating resistor must be connected to the robot base. For detailed information, refer to 7.4.1Installation instructions.

<p align="center">
    <img src="../_assets/7.2_figure_1.png" width="500"> </img>
</p>

There must be no obstacles, fences, or other objects within the detection zone that could interfere with object detection. Caution is required as obstacles or fences installed in front of the sensor may cause false or missed detections.

<p align="center">
    <img src="../_assets/7.2_figure_2.png" width="300"> </img>
</p>

False or missed detections may occur depending on the floor material where the robot is installed. To mitigate detection errors caused by the floor, ensure the robot is installed at a sufficient height above the ground so that the sensor does not detect the floor surface.

<p align="center">
    <img src="../_assets/7.2_figure_3.png" width="1000"> </img>
</p>

[__SOURCE](7-Sensor_Usage_and_Installation/7-3-Proper_usage_of_external_radar_sensor.md)
## 7.3	Proper usage of external radar sensor
The external radar sensor must be used only when its position is securely fixed. If the sensor shakes or its position is arbitrarily changed, false or missed detections may occur, and in particular, the safety function may fail to operate normally.

<p align="center">
    <img src="../_assets/7.3_figure_1.png" width="700"> </img>
</p>

There must be no obstacles or moving objects within the sensor's front detection zone that could interfere with object detection. Caution is required as obstacles installed in front of the sensor may cause false or missed detections.

<p align="center">
    <img src="../_assets/7.3_figure_2.png" width="700"> </img>
</p>

Floor materials can affect sensor performance, potentially leading to false or missed detections. If floor-induced detection errors are anticipated, ensure that the sensor does not scan the ground by either elevating the sensor position at a sufficient distance above the floor or adjusting its installation angle.

<p align="center">
    <img src="../_assets/7.3_figure_3.png" width="700"> </img>
</p>

[__SOURCE](7-Sensor_Usage_and_Installation/7-4-Installation_of_the_external_radar_sensor/README.md)
## 7.4	Installation of the external radar sensor
If there is a risk of an object approaching a blind spot that cannot be detected by the built-in radar, additional safety measures are required to prevent accidents. As one of the solutions, an external radar sensor can be installed to expand the detection zone; examples of this setup are provided below. However, please note that these are only selected examples, and appropriate measures must be taken based on the actual working environment.

[__SOURCE](7-Sensor_Usage_and_Installation/7-4-Installation_of_the_external_radar_sensor/7-4-1-Installation_instructions.md)
### 7.4.1	Installation instructions
- Non-installation of external radar sensors (Built-in radars only)
Connect a terminating resistor to the XRS connector on the rear of the robot base.

<p align="center">
    <img src="../../_assets/7.4.1_figure_1.png" width="150"> </img>
</p>

-   Connection method for installing a single external radar <br>
Connect the XRS connector on the rear of the robot base to one of the connectors on the rear of the external radar using a cable. Attach a terminating resistor to the remaining connector of the external radar.

<p align="center">
    <img src="../../_assets/7.4.1_figure_2.png" width="350"> </img>
</p>

- Connection method for installing two external radars <br>
Connect the XRS connector on the rear of the robot base to one of the connectors on the rear of the first external radar using a cable. Connect the remaining connector of the first external radar to the second external radar with another cable. Finally, attach a terminating resistor to the vacant connector of the second external radar. In other words, the terminating resistor must be attached to the external radar located at the furthest end of the cable wiring.

<p align="center">
    <img src="../../_assets/7.4.1_figure_3.png" width="550"> </img>
</p>

[__SOURCE](7-Sensor_Usage_and_Installation/7-4-Installation_of_the_external_radar_sensor/7-4-2-Outside_of_the_robot's_operating_range.md)
### 7.4.2	Outside of the robot ‘s operating range
Since false detections may occur if the robot obstructs or passes in front of the built-in radar sensor, the robot’s operating range must be excluded from the detection zone. However, this configuration creates a limitation where objects approaching the robot from outside the robot working area cannot be detected. To compensate for this limitation of the built-in sensor, an additional external radar sensor can be installed, and its detection zone should be configured to cover the area outside the robot’s operating range.

<p align="center">
    <img src="../../_assets/7.4.2_figure_1.png" width="600"> </img>
</p>
[__SOURCE](7-Sensor_Usage_and_Installation/7-4-Installation_of_the_external_radar_sensor/7-4-3-Around_obstacles.md)
### 7.4.3	Around obstacles
To prevent degradation of sensor detection performance, surrounding obstacles such as fences, pillars, and walls must be excluded from the detection zone. This may result in a reduced detection zone; if the detection zone needs to be expanded further to ensure safety, an external radar sensor can be installed to compensate. 

<p align="center">
    <img src="../../_assets/7.4.3_figure_1.png" width="600"> </img>
</p>
[__SOURCE](7-Sensor_Usage_and_Installation/7-4-Installation_of_the_external_radar_sensor/7-4-4-Installing_the_robot_on_a_wall_or_ceiling.md)
### 7.4.4	Installing the robot on a wall or ceiling
If the robot is installed on a wall or ceiling instead of the floor, blind spots where objects cannot be detected by the built-in radar sensor alone may occur. Therefore, safety measures can be established by installing additional external radar sensors in areas where objects are expected to approach.

<p align="center">
    <img src="../../_assets/7.4.4_figure_1.png" width="600"> </img>
</p>

<p align="center">
    <img src="../../_assets/7.4.4_figure_2.png" width="600"> </img>
</p>

[__SOURCE](7-Sensor_Usage_and_Installation/7-5-Examples_of_proper_sensor_placement_for_safety_function_operation.md)
## 7.5	Examples of proper sensor placement for safety function operation
The figure below illustrates examples of normal operation and malfunction of the safety function depending on the detected part of the object. Since sensor performance is influenced by the installation position and environment, sensors must be placed to suit the specific working environment by referring to the examples below. You must thoroughly review the surface area of the target object and the sensor's detection range to ensure that a sufficient detected surface area of the object is secured.

<p align="center">
    <img src="../_assets/7.5_figure_1.png" width="700"> </img>
</p>

<p align="center">
    <img src="../_assets/7.5_figure_2.png" width="700"> </img>
</p>

<p align="center">
    <img src="../_assets/7.5_figure_3.png" width="350"> </img>
</p>

[__SOURCE](8-Configuration_and_Operation/README.md)
# 8	Configuration and operation
[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/README.md)
## 8.1	Configuration procedure

{% hint style="danger" %}  
The initial configuration of the system must be performed only by authorized personnel. Before configuring the system, it must be verified that the robot controlled through this system operates as intended.
{% endhint %}
[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-1-Detection_area_configuration.md)
### 8.1.1	Detection area configuration
Go to [system] – [10. Safety System] – [Safety Radar] - [radar sensor setting] menu to configure the detection zone. 
-	Tabs 1 to 6: Up to six radar sensors can be used. Tabs 1 to 4 represent the built-in radars installed on the robot base, while Tabs 5 and 6 represent the external radars. The installation locations of the built-in radars are shown in the figure below.

<p align="center">
    <img src="../../_assets/8.1.1_figure_1.png" width="200"> </img>
</p>

-	Active: Enables or disables the radar sensor
-	zone1: When the built-in radar sensor is enabled, Zone 1 (the stop zone) is automatically enabled. The value entered for zone1 is its start point, and its end point is equal to the start point of the next enabled zone. For example, if the start point of Zone 1 is set to 500, Zone 2 is disabled, and Zone 3 is enabled with a start point of 2000, the range for Zone 1 will be 500 to 2000 mm.
-	zone2 ~ 4: Enter the start point for each zone; the start point of the next enabled zone serves as the end point of the previous zone. For example, if zone2 is set to 1000 and zone3 is set to 2000 and enabled, the range for zone2 is configured from 1000 to 2000 mm. When a moving object is detected within zones 2 to 4, a robot deceleration signal is output. The input range is 1000 to 5000. 
-	End point: Sets the end point of the last zone. The input range is 500 to 5000.
-	Valid azimuth start/end: Sets the start and end of angles of the detection zone. The input range is -55° to 55°.

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-2-Radar_replan.md)
### 8.1.2	Radar replan
Go to [system] – [10. Safety System] – [Safety Radar] - [Safety radar replan setting] menu to set the deceleration ratio when an object is detected in zones 2 ~ 4.
-	Replan: Enables or disables the robot stop/deceleration function upon object detection.
-	speed detection delay time: Sets the delay time before verifying if the robot meets the speed limit after deceleration. In other words, the system starts checking whether the speed limit is met after this delay time has elapsed.
-	zone2 ~ zone4
    -   Limit Speed: Sets the speed limit for the robot after deceleration. If the robot exceeds this speed limit during deceleration, it will stop.
    -   SpeedRate: Sets the deceleration ratio of the robot.

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-3-Radar_detection_monitoring.md)
### 8.1.3	Radar detection monitoring
Navigate to [system] – [10. Safety System] – [Safety Radar] - [Radar detection monitoring] to view objects detected within the detection zone. Each radar sensor displays a maximum of two detected objects. Detected objects per radar are organized into tabs, as shown below.
-	Built-in(1) tab: Built-in radars 1 and 3
-	Built-in(2) tab: Built-in radars 2 and 4
-	External tab: External radars 5 and 6

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-4-Radar_object_detection_parameter.md)
### 8.1.4	Radar object detection parameter
Navigate to [system] – [10. Safety System] – [Safety Radar] - [Radar object detection parameter] menu to configure object detection parameters. Detection performance depends on the configured values. After setting the parameters, ensure to verify proper operation and perform a risk assessment.
-	epsilon: Represents the distance between points for clustering, used to distinguish between core points and outliers. If the distance between points is less than this value, they are processed as a cluster.
-	min point: The minimum number of points needed to create a cluster.
-	max speed: Represents the maximum speed of points to be grouped into a cluster. Higher values enable the detection of fast-moving objects, while lower values prevent the detection of objects moving faster than the set speed.
-	hit active: Specifies the minimum number of consecutive frames needed for object recognition. Increasing this value enhances detection reliability but reduces detection speed. Decreasing this value may cause false detections due to noise.
-	hit stop: Represents the maximum number of frames a detected object can persist without receiving new data.
-	idis: Specifies the minimum moving distance needed for object detection. Increasing this value enhances detection reliability but reduces detection speed. Decreasing this value may cause incorrect detection due to noise.
-	tracker radius: Represents the maximum radius for updating an object's position. If the next position of a detected object is within this value, the system tracks its location; if it falls outside, tracking stops. Higher values stabilize object tracking but may cause paths to blend with those of other objects. Conversely, lower values may lead to a loss of track, causing the same object to be redundantly detected as a new one.

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-5-Radar_version_information.md)
### 8.1.5	Radar version information
Enter engineering mode and go to [system] – [10. Safety System] – [Safety Radar] - [Radar version information] to check the radar-related information.


[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-6-Safety_function_verification/README.md)
### 8.1.6	Safety function verification
Since the system can operate in various environments, the installer must verify that the detection zones are properly configured and that the safety functions work as intended after installation and initial setup. 

{% hint style="danger" %}
A system that has not completed verification does not guarantee the operation of safety functions. Even if not mentioned in the verification details below, if there are specific characteristics of the environment in which the system operates, they must be added to the verification details to define the mandatory tests. All verification contents shall be recorded as data for future proof.
{% endhint %}

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-6-Safety_function_verification/8-1-6-1.md)
#### 8.1.6.1	Access detection function verification procedure
When the system is operated under test conditions, the access detection safety function must activate, and no factors should exist in the operating environment that could degrade the performance of the access detection function. The following requirements apply when verifying the access detection function:
-	During verification, the object to be detected must move within the maximum detectable speed, and it must not stop or move at a slow speed.
-	The detection target must not be occluded during verification.
-	All verification participants must be aware of the spatial boundaries of the configured stop zone and warning zone.

Verification of the access detection function must begin under the following conditions to ensure the safety of the detection target and the accuracy of the verification:
-	The access detection function is activated.
    -   Radar sensor setting – Activate by sonsor
    -   Radar replan – Activate “Replan” and enter a value less than 100 for “SpeedRate”
    -   Radar object detection parameter – Enter each parameter
-	The system is properly connected.
    -   Radar version information – CAN status: Conn.
-	For safe operation, the verification must be conducted by a team of at least two people. One worker shall act as the detection target, while the other must stand by to respond immediately to any potential emergency caused by a failure to detect. The person acting as the detection target must remain outside the robot's operating range at all times.

The test procedure for verifying the access detection function under normal conditions is as follows. If there are unique environmental characteristics that are difficult to verify using only the conditions below, additional mandatory test items must be defined to reflect them, and the corresponding test conditions and results shall be recorded in detail.

<p align="center">
    <img src="../../../_assets/8.1.6.1_figure_1.png" width="500"> </img>
</p>

-	Access points #1 through #5 indicate the entry locations and approach directions of the detection target. The detailed entry locations are described below, and the approach directions follow the indicated arrows. If there are additional points that require verification due to the worker's movement, obstacles generated during robot operation, or unique environmental characteristics of the site—even if not explicitly specified—they must be included in the test.
    -   #1: End of zone & start of angle
    -   #2: End of zone & midpoint of angle
    -   #3: End of zone & end of angle
    -   #4: Midpoint of zone & start of angle
    -   #5: Midpoint of zone & end of angle
-	The test procedure is as follows:
1.	Power on and start the system
2.	Activate the access detection function, and verify that the system is successfully connected
3.	Operate the robot that do not obstruct the front of the radar sensor
4.	The detection target enters the detection zone through access point #1
5.	Verify whether the robot stops or decelerates according to the zone type
6.	Repeat steps 3 through 5 for all access points

[__SOURCE](8-Configuration_and_Operation/8-1-Configuration_procedure/8-1-6-Safety_function_verification/8-1-6-2.md)
#### 8.1.6.2	Restart prevention function verification procedure
When the system is operated under test conditions, the restart prevention function must activate, and no factors should exist in the operating environment that could degrade the performance of the restart prevention function. The following requirements apply when verifying the restart prevention function:
-	The robot must remain stopped or decelerated by the access detection function.
-	All verification participants must be aware of the spatial boundaries of the configured stop zone and warning zone.

Verification of the restart prevention function must begin under the following conditions to ensure the safety of the detection target and the accuracy of the verification:
-	The access detection function is activated.
    -   Radar sensor setting – Activate by sonsor
    -   Radar replan – Activate “Replan” and enter a value less than 100 for “SpeedRate”
    -   Radar object detection parameter – Enter each parameter
-	The system is properly connected.
    -   Radar version information – CAN status: Conn.
-	For safe operation, the verification must be conducted by a team of at least two people. One worker shall act as the detection target, while the other must stand by to respond immediately to any potential emergency caused by a failure to detect. The person acting as the detection target must remain outside the robot's operating range at all times.

The test procedure for verifying the restart prevention function under normal conditions is as follows. If there are unique environmental characteristics that are difficult to verify using only the conditions below, additional mandatory test items must be defined to reflect them, and the corresponding test conditions and results shall be recorded in detail.


<p align="center">
    <img src="../../../_assets/8.1.6.2_figure_1.png" width="500"> </img>
</p>

-	Access points #1 through #5 indicate the entry locations and approach directions of the detection target. The detailed entry locations are described below, and the approach directions follow the indicated arrows. If there are additional points that require verification due to the worker's movement, obstacles generated during robot operation, or unique environmental characteristics of the site—even if not explicitly specified—they must be included in the test.
    -   #1: End of zone & start of angle
    -   #2: End of zone & midpoint of angle
    -   #3: End of zone & end of angle
    -   #4: Midpoint of zone & start of angle
    -   #5: Midpoint of zone & end of angle
-	The test procedure is as follows:
1.	Power on and start the system
2.	Activate the access detection function, and verify that the system is successfully connected
3.	Operate the robot that do not obstruct the front of the radar sensor
4.	The detection target enters the detection zone through access point #1
5.	Verify whether the robot stops or decelerates according to the zone type
6.	Check if the robot status is maintained
7.	The detection target moves outside all detection zones
8.	Apply a restart signal, and verify that the robot operates normally
9.	Repeat steps 3 through 8 for all access points


[__SOURCE](8-Configuration_and_Operation/8-2-Troubleshooting_for_system_configuration/README.md)
## 8.2	Troubleshooting for system configuration
This section describes general methods for resolving issues identified during safety function verification. However, issues arising from unique environmental characteristics in which the system operates may not be resolved using this method.

[__SOURCE](8-Configuration_and_Operation/8-2-Troubleshooting_for_system_configuration/8-2-1-Robot_not_stopping_or_decelerating_despite_object_entering_detection_zone.md)
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

[__SOURCE](8-Configuration_and_Operation/8-2-Troubleshooting_for_system_configuration/8-2-2-Robot_not_operating_normally_despite_detection_target_moving_outside_detection_zone.md)
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

[__SOURCE](9-Maintenance/README.md)
# 9	Maintenance
[__SOURCE](9-Maintenance/9-1-Maintenance_of_the_operating_environment.md)
## 9.1	Maintenance of the operating environment

{% hint style="warning" %}
Contamination such as dust, oil, or moisture on the sensor's protective case (radome) may degrade the system's detection performance. To prevent malfunctions, the radome must be inspected and maintained periodically to ensure it remains free of contaminants.
{% endhint %}

[__SOURCE](9-Maintenance/9-2-Troubleshooting.md)
## 9.2	Troubleshooting
If any issues occur during system operation, refer to the table below to identify the cause and apply the recommended corrective actions. If the problem persists after applying the suggested solutions, please contact the support team for further assistance.

<table>
  <thead>
    <tr>
      <th style="text-align: center;">Issue</th>
      <th style="text-align: center;">Cause</th>
      <th style="text-align: center;">Solution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>An object is detected even when it is outside the detection zone</td>
      <td>Mismatch between the desired and actual detection zones</td>
      <td>Reset the detection zone by referring to 5.2Detection area</td>
    </tr>
    <tr>
      <td>The system transitions to a safe state despite no object in the detection area</td>
      <td>Failure of the control unit or one or more sensor units</td>
      <td>Check for system errors (see Error Description section)</td>
    </tr>
    <tr>
      <td rowspan="2">The system does not operate properly</td>
      <td>Control unit malfunction</td>
      <td>Check for system errors (see Error Description section)</td>
    </tr>
    <tr>
      <td>Sensor unit malfunction</td>
      <td>Check for system errors (see Error Description section)</td>
    </tr>
  </tbody>
</table>

[__SOURCE](9-Maintenance/9-3-Error_description/README.md)
## 9.3	Error description
When a system fault is detected, an error code will be displayed on the TP. This section provides descriptions of each error code, including their meanings and possible causes.

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-1-Control_unit_self-diagnostic_errors.md)
### 9.3.1	Control unit self-diagnostic errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54301|Diagnostic error on the Sensor Interface board MCU|The hardware logic of the MCU is abnormal|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54302|Interrupt diagnostic error on the Sensor Interface board|MCU interrupt address mismatch detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54303|CPU register diagnostic error on the Sensor Interface board|Read,write operation abnormality in the CPU1 core register|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54304|FPU register diagnostic error on the Sensor Interface board|Read,write abnormality in the CPU1 FPU register|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54305|VCRC register diagnostic error on the Sensor Interface board|Read,write abnormality in the CPU1 VCRC register|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54306|RAM diagnostic error on the Sensor Interface board|Read,write abnormality in the MCU RAM|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54307|RAM diagnostic error on the Sensor Interface board|Read,write abnormality in the MCU RAM copy area|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54308|Flash diagnostic error on the Sensor Interface board|MCU Flash CRC mismatch detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54309|Oscillator diagnostic error on the Sensor Interface board|Abnormality in the Sensor Interface board's external oscillator|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54311|Boot Flash CRC error on the Sensor Interface board|Boot Flash CRC mismatch on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54312|Program RAM CRC error on the Sensor Interface board|RAM CRC mismatch on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54353|SDRAM Read/Write Error on Sensor Interface Board|The SDRAM status on the sensor interface board is abnormal|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-2-Control_unit_power_supply_errors.md)
### 9.3.2	Control unit power supply errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54314|24V voltage error on the Sensor Interface board|24V voltage issue detected on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54315|EX24V voltage error on the Sensor Interface board|EX24V voltage issue detected on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54316|3V3 voltage error on the Sensor Interface board|3.3V voltage issue detected on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54317|1V2 voltage error on the Sensor Interface board|1.2V voltage issue detected on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-3-Control_unit_cross_check_errors.md)
### 9.3.3	Control unit cross check errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54323|Cross-check error in the Sensor Interface board diagnostic functions|Diagnostic result mismatch between MCUs|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54324|Sensor Interface board Temperature sensor measurement error|Temperature deviation between sensors exceeds 15°C|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54325|Synchronization error detected on Sensor Interface board CPU1|Synchronization issue detected on Sensor Interface board CPU1|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54326|Overheat detected on Sensor Interface board temperature sensor|Board temperature exceeds the safety threshold|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-4-Control_unit_sequence_diagnosis_errors.md)
### 9.3.4	Control unit sequence diagnosis errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54331|Program execution sequence error on the Sensor Interface board|The program execution sequence deviates from the expected flow|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54332|Program execution sequence error on the Sensor Interface board|The program execution sequence deviates from the expected flow|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54333|Program execution sequence cross-check error on the Sensor Interface board|Inter-MCU program execution sequence mismatch detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54334|Program execution timeout error on the Sensor Interface board|Program execution time deviates from the expected duration|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54335|Program execution measurement error on the Sensor Interface board|Abnormal program operation detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-5-Control_unit_watchdog_errors.md)
### 9.3.5	Control unit watchdog errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54341|Cross-check error detected in Sensor Interface board operation|Operational anomaly detected in the redundant MCU|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54342|External watchdog malfunction detected on the Sensor Interface board|Operational anomaly detected in the external watchdog timer|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-6-Control_unit_version_errors.md)
### 9.3.6	Control unit version errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54351|Firmware version mismatch detected on the Sensor Interface board|Firmware version mismatch detected on the Sensor Interface board|1) Please proceed with the firmware update<br>2) If the problem persists, replace the sensor Interface board|
|E54352|CPU1 Firmware version mismatch detected on the Sensor Interface board|Firmware version mismatch detected on the Sensor Interface board|1) Please proceed with the firmware update<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-7-Control_unit_FSI_communication_errors.md)
### 9.3.7	Control unit FSI communication errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54450|FSI (Fast Serial Interface) synchronization error detected on the Sensor Interface board|FSI synchronization error detected on the Sensor Interface board|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54451|Internal communication (FSI) error detected on the Sensor Interface board|Internal communication (FSI) error detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|
|E54452|FSI initialization and ping test failure detected on the Sensor Interface board|FSI initialization and ping test failure detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor Interface board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-8-Sensor_unit_CAN-FD_communication_errors.md)
### 9.3.8	Sensor unit CAN-FD communication errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54504|Radar sensor ID mismatch detected|The responded ID does not match the requested value|1) Reboot the controller<br>2) If the problem persists, replace the sensor board|
|E54505|CRC error detected in radar sensor data response|Data corruption detected in the radar sensor response|1) Reboot the controller<br>2) If the problem persists, replace the sensor board|
|E54506|CRC error detected during radar sensor data request|Data corruption detected during the radar sensor request sequence|1) Reboot the controller<br>2) If the problem persists, replace the sensor board|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-9-Sensor_unit_status_errors.md)
### 9.3.9	Sensor unit status errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54550|Radar sensor status cross-check error detected|Radar sensor status inconsistency detected|1) Reboot the controller<br>2) If the problem persists, replace the sensor sensor|
|E54554|Radar sensor detection data inconsistency detected|Consecutive detection data inconsistency detected on the radar sensor|1) Please check for any objects obstructing the radar sensor<br>2) If the problem persists, replace the radar sensor|
|E54555|CAN communication error detected on radar sensor|Data duplication and packet loss detected|1) Please replace the corresponding radar sensor<br>2) If the problem persists, replace the radar sensor|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-10-Sensor_power_supply_error.md)
### 9.3.10	 Sensor power supply error
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54560|24V power supply error detected on radar sensor|24V power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54561|5V power supply error detected on radar sensor|5V power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54562|3V3 power supply error detected on radar sensor|3V3 power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54563|1V8 power supply error detected on radar sensor|1V8 power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54564|1V2 power supply error detected on radar sensor|1V2 power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54565|1V power supply error detected on radar sensor|1V power supply error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-11-Sensor_unit_diagnosis_errors.md)
### 9.3.11	Sensor unit diagnosis errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54566|Over-temperature error detected on radar sensor|Over-temperature error detected on the radar sensor|1) Please turn off the sensor power for 5 minutes<br>2) If the problem persists, replace the radar sensor|
|E54567|Diagnostic failure detected on radar sensor|Diagnostic function error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54568|Boot diagnostic failure detected on radar sensor|Diagnostic function error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|
|E54569|Overall diagnostic failure detected on radar sensor|Diagnostic function error detected on the radar sensor|1) Reboot the controller<br>2) If the problem persists, replace the radar sensor|

[__SOURCE](9-Maintenance/9-3-Error_description/9-3-12-Sensor_unit_version_errors.md)
### 9.3.12	Sensor unit version errors
|Code|Message|Cause|Remedy|
|:--|:--|:--|:--|
|E54570|Version mismatch detected on radar sensor|Radar sensor is running an outdated firmware version|1) Please update the sensor firmware to the latest version<br>2) If the problem persists, replace the radar sensor|
|E54571|Radar sensor is running an outdated firmware version|The radar sensor is running an outdated firmware version|1) Please update the sensor firmware to the latest version<br>2) If the problem persists, replace the radar sensor|

[__SOURCE](9-Maintenance/9-4-Control_unit_firmware_update.md)
## 9.4	Control unit firmware update
1.	Download the latest release version onto a USB drive.
2.	Connect the USB drive to the port located on the right side of the TP.
3.	Update the version using the TP's version update function.

[__SOURCE](9-Maintenance/9-5-Sensor_replacement.md)
## 9.5	Sensor replacement
If a critical error is detected in one or more sensor units and the issue persists even after corrective actions are taken, the sensor unit must be replaced. If the sensor unit needs to be replaced, contact the customer support team.

[__SOURCE](10-Specifications/README.md)
# 10	Specifications
[__SOURCE](10-Specifications/10-1-Global_specifications.md)
## 10.1	Global specifications

|Item|Specification|
|:--|:--|
|Detection method|Motion detection using FMCW radar|               
|Frequency|60GHz|
|Detection range|500mm ~ 5000mm|
|Minimum RCS| 0.17|
|Field of view (FOV)| -55° ~ 55°|
|Guaranteed response time|300ms|
|Operating altitude|Up to 1000m|
|Operating humidity|20% ~ 95%|
|Operating temperature|0℃ ~ 45℃|
|Noise level|Below 70dB (negligible)|
|Storage temperature|-20℃ ~ 60℃|
|Storage altitude|Up to 12,000m|
|IP rating|IP 20|

{% hint style="danger" %}
Guaranteed response time: Not guaranteed during verification or update.<br>
IP rating: Compliance is ensured when the system is mounted on the mechanical structure. If the system is arbitrarily disassembled and used separately, the corresponding rating cannot be guaranteed.
{% endhint %}

[__SOURCE](10-Specifications/10-2-Safety_parameters.md)
## 10.2	Safety parameters

|Parameter|Value|Standard / remark|
|:--|:--|:--|
|SIL|2|
|HFT|1|
|ESPE|3|According to IEC/TS 61496-5:2023|
|Category|3|According to ISO 13849:2023|
|PL|d|
|DC<sub>avg</sub>|Medium (90%)|
|MTTF|≥10 years and <30 years|
|MRT|≤20 minutes|
|SC|2|

[__SOURCE](10-Specifications/10-3-System_characteristics.md)
## 10.3	System characteristics

|Component|Specification|Remark|
|:--|:--|:--|
|Control unit safety output|Output signal switching device<br>Dual safety output|
|Control unit safety input|Dual-channel digital input|Uses common ground|
|Power supply|24V DC|
|Outdoor use|Not recommended|

{% hint style="danger" %}
Outdoor use: Safety and normal operation not guaranteed for outdoor use
{% endhint %}
[__SOURCE](10-Specifications/10-4-Software/README.md)
# 10.4	Software
[__SOURCE](10-Specifications/10-4-Software/10-4-1-System_configuration_software.md)
### 10.4.1	System configuration software
 The system software is developed in compliance with IEC 61508-3. It is embedded in the hardware and does not require integration or configuration by the user upon initial installation. Firmware update packages are managed by the manufacturer, and digital signatures are used to prevent the use of unauthorized binary files.

{% hint style="danger" %}
Modification, alteration, addition, or removal of firmware on the sensor unit or control unit is strictly prohibited. Any unauthorized changes may compromise the safety function, and the manufacturer shall not be held responsible for any issues resulting from such actions.
{% endhint %}

[__SOURCE](10-Specifications/10-4-Software/10-4-2-EtherCAT.md)
### 10.4.2	EtherCAT
 EtherCAT is a registered trademark and patented technology licensed by Beckhoff Automation GmbH, Germany.

