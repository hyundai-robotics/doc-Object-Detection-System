### 4.2.1	Sensor unit – Control unit communication
The sensor units and the control unit communicate using a CAN-FD bus. Communication between the sensor units and the control unit is diagnosed to ensure compliance with SIL 2 and PL d levels. Multiple sensor units connected to a single control unit must have unique IDs. The built-in sensor units are assigned IDs based on their installation locations, as shown in the figure below. <br>
The IDs are configured as follows. The ID is configured using the 4-pin switch on each sensor unit. Odd-numbered IDs are assigned to Part A, and even-numbered IDs are assigned to Part B. Each switch pin has the following value: <br>
- Pin 4: 1
- Pin 3: 2
- Pin 2: 4
- Pin 1: 8

 Set the pins corresponding to the desired ID to ON. For example, to assign IDs 7 and 8 to the sensor units, set pins 2, 3, and 4 in Part A and pin 1 in Part B to ON, as shown in the figure below.

<p align="center">
    <img src="../../_assets/4.2.1_figure_1.png" width="500"> </img>
</p>