# Object Detection System

## 4.3 Communication

### 4.3.1 Communication Between Sensor Unit and Control Unit

The sensor unit and the control unit communicate using the CAN-FD bus. Communication between the sensor unit and the control unit is verified through diagnostics to guarantee SIL 2 and PL d levels. Multiple sensor units connected to one control unit must each have a unique ID. The control unit and sensor units communicate using unique IDs. By default, the sensor unit is assigned an ID based on its installation location.

### 4.3.2 Communication Between Control Unit and Robot’s Safety-Related Main Control System

The control unit and the robot’s safety-related main control system communicate using FSoE based on EtherCAT. FSoE complies with the IEC 61508 standard and guarantees up to SIL 3 level. All safety-related parameters are managed by the robot’s safety-related main control system, and the control unit receives and uses them when necessary. The TP, which allows the user to control parameters, is also connected to the robot’s safety-related main control system. When safety-related parameters are transmitted to the control unit, verification is performed to ensure proper values, thereby guaranteeing SIL 2 and PL d levels.
