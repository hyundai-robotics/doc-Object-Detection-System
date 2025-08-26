# Object Detection System

## 5.1 Sensor

### 5.1.1 Sensor Operating Principle
The sensor unit consists of two independent sensors. These are FMCW radar devices that use continuously frequency-modulated signals to measure the position of moving objects within the detection area. A continuous wave emitted from the FMCW radar transmitter collides with an object and is reflected back to the receiver. Since the transmitted signal changes frequency over time, a frequency difference occurs when compared to the received reflected signal. This frequency difference is converted into the distance to the object through Doppler shift.

### 5.1.2 Factors Affecting Detection Performance

![Warning Symbol](../_assets/경고기호.png)

If a conductive/metallic object is located in front of the sensor, the signal cannot penetrate it, which may affect object detection performance. If there is a high probability that conductive/metallic objects will be detected as objects in the operating environment, the operation of the system must be revalidated.

### 5.1.3 Factors Affecting Reflected Signals

![Warning Symbol](../_assets/경고기호.png)

The size of the reflected signal may vary depending on the characteristics and material of the detected object. This affects system operation, so even in safe situations, safety functions may be triggered. The impact of objects primarily detected in the operating environment on the reflected signal must be considered to optimize performance.
- Size: Larger objects reflect more signals with stronger intensity. Smaller objects may produce weaker signals.
- Shape: Smooth surfaces (e.g., metal plates) tend to reflect signals directly or focus reflections. Irregular or rough surfaces scatter signals in multiple directions, weakening the returned signal strength.
- Material: Highly reflective metals or dense materials generate stronger reflected signals. Absorptive materials (e.g., plastics, rubber, fabric) may weaken signal strength.
- Speed: If the object is moving too fast or too slow, errors may occur in signal analysis.
- Multipath Effect: Other surrounding surfaces (e.g., walls, floors) may reflect signals, causing additional signals to be received.

### 5.1.4 Detectable and Undetectable Objects

![Warning Symbol](../_assets/경고기호.png)

In general, the sensor only measures moving objects within the detection range. For humans, even if movement is not visually noticeable, static residual movements such as heartbeat or breathing exist. These are detected as upper body movements, so as long as the person’s upper body is within the sensor’s detection range, measurement is possible. For objects, only those moving at detectable speeds within the detection area are considered. Completely stationary objects are not guaranteed to be detected.
Within the robot’s operating range, the robot arm moves, so objects detected in this range are intentionally ignored. Therefore, objects falling into the detection area from above or from the robot’s direction into its operating range will not be detected.

#### Detection Target Limitations

Minimum human dimensions detectable by the collaborative robot radar system:
* Height: 1640 mm
* Chest thickness: 200 mm (at least 200 mm of the upper body width must be exposed toward the radar sensor direction)
* Height and chest thickness must be greater than these minimums to ensure detection
* Only standing upright posture without bending is guaranteed to be detected, not sitting or crouching individuals

These criteria are based on the average anthropometric measurements of Korean people according to ISO 7250-1 standard.

### Table 10 - Summary of Korean Statistics

| No.     | KS A ISO 7250-1 Measurement | Category | Sample Size | Mean   | Std. Dev. | P1   | P5   | P50  | P95  | P99  |
|---------|------------------------------|----------|-------------|--------|-----------|------|------|------|------|------|
| 2.4.1.2 | Height                       | Male     | 2613        | 1707.6 | 62.3      | 1564 | 1608 | 1708 | 1805 | 1847 |
|         |                              | Female   | 2614        | 1579.4 | 54.8      | 1453 | 1491 | 1577 | 1670 | 1707 |
|         |                              | Total    | 5227        | 1643.3 | 86.7      | 1496 | 1511 | 1640 | 1787 | 1837 |
| 9.4.19  | Chest Thickness              | Male     | 2613        | 211.3  | 19.0      | 170  | 181  | 210  | 244  | 261  |
|         |                              | Female   | 2614        | 189.2  | 19.7      | 151  | 160  | 187  | 224  | 244  |
|         |                              | Total    | 5227        | 200.2  | 22.3      | 155  | 165  | 200  | 237  | 256  |
