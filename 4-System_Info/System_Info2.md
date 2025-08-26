# Object Detection System

## 4.2 System Configuration

### 4.2.1 System Parameters

The parameters used in the system are managed through the control unit. If no specific settings are made during installation, the system parameters are set to default values. The system parameters can be modified using the Teach Pendant (TP). The typical configuration and default values of parameters that can be monitored by the system user are as follows:  

| Parameter            | Min  | Max  | Default | Remarks                     |
|----------------------|------|------|---------|-----------------------------|
| **Detection Area Info** |      |      |         |                             |
| Area ID              | 1    | 5    | Unique ID | Modification not recommended |
| Activation           | 0    | 1    | 1       | 0 = Disabled, 1 = Enabled   |
| Measurement Start Distance | 0 | 5000 | 0     | Unit: mm                    |
| Measurement End Distance   | 0 | 5000 | 5000  | Unit: mm                    |
| Warning Start Distance     | 0 | 5000 | 2000  | Unit: mm                    |
| Measurement Start Azimuth  | 0 | 180  | 0     | Unit: °                     |
| Measurement End Azimuth    | 0 | 180  | 180   | Unit: °                     |

| Parameter            | Min  | Max  | Default | Remarks                     |
|----------------------|------|------|---------|-----------------------------|
| **Sensor Info**      |      |      |         |                             |
| Sensor ID            | 1    | 8    | Unique ID | Modification not recommended |
| Activation           | 0    | 1    | 1       | 0 = Disabled, 1 = Enabled   |
| Measurement Angle    | -    | -    | -       | Value received from sensor (Read only) |
| Sensor x Coordinate  | -    | -    | -       |                             |
| Sensor y Coordinate  | -    | -    | -       |                             |
| Sensor z Coordinate  | -    | -    | -       |                             |
| Sensitivity          | TBD  | TBD  | TBD     |                             |

![Warning Symbol](../_assets/경고기호.png)

System parameters directly affect operating performance. Therefore, after initial setup or any changes, the system must be tested to verify proper operation. The measurement start distance must be set outside the robot’s operating range to prevent malfunction. The measurement distance and sensitivity should be set by considering the speed, material, and other properties of major objects likely to approach in the robot’s operating environment.  

### 4.2.2 Access Rights

The access rights for each type of user for this system are as follows:  

| Category            | General User | Operator | Engineer | Administrator |
|---------------------|--------------|----------|----------|---------------|
| System Monitoring   | X            | X        | X        | X             |
| Parameter Setting   |              | X        | X        | X             |
| Log File Download   |              | X        |          |               |
| Parameter File Backup/Restore |   |          | X        | X             |
| Network Configuration |          |          |          | X             |
| Firmware Update     |              |          |          | X             |
| Technical Support & Maintenance | |          | X        |               |

### 4.2.3 System Configuration via Application

System configuration via the application must be performed by authorized installers or maintenance personnel. Depending on the target device, the control unit or sensor unit must be connected to a computer to use the application. Using the application allows modification of all system parameters, including those specified in this document. Therefore, system operation must be verified after configuration. The application performs the following functions:  
- System configuration  
- System function verification  
- Checking system logs and generating reports  

### 4.2.4 System Configuration via TP

For system parameters where the user has modification rights, the TP is used to control them. Among the parameters, the ID values contain unique information. Among the parameters, the sensor coordinates indicate the installation angle of the sensor, which must be recorded at initial installation. Arbitrary modification of this value cannot guarantee proper operation of the system.  
