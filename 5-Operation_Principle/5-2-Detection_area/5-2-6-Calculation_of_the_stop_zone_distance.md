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

