# Object Detection System

## 10.3 Error Description

When a system error is diagnosed, an error code is displayed on the TP (Teach Pendant).  
This section explains the meaning and causes of each error code【289†source】.

### 10.3.1 Self-Diagnosis Errors

| Code   | Meaning                               |
|--------|---------------------------------------|
| E54301 | **HWBIST** self-test failure          |
| E54302 | **PIE RAM** error detected            |
| E54303 | **CPU** register error detected       |
| E54304 | **FPU** (Floating Point Unit) register error detected |
| E54305 | **VCRC** register error detected      |
| E54306 | RAM copy error                        |
| E54307 | RAM integrity check failure           |
| E54308 | Flash CRC error detected              |
| E54309 | Oscillator (clock) error detected     |
| E54310 | Flash CRC value overflow              |
| E54311 | Boot flash CRC error                  |
| E54312 | Boot RAM CRC error                    |
| E54313 | Initial watchdog timer error          |

---

### 10.3.2 Power Errors

| Code   | Meaning                    |
|--------|----------------------------|
| E54314 | 24V power error detected   |
| E54315 | External 24V power error   |
| E54316 | 3.3V power error detected  |
| E54317 | 1.2V power error detected  |

---

### 10.3.3 Sensor Initialization Errors

| Code   | Meaning                         |
|--------|---------------------------------|
| E54318 | Radar configuration data error  |

---

### 10.3.4 Cross-Check Errors

| Code   | Meaning                                 |
|--------|-----------------------------------------|
| E54322 | Safety result mismatch error            |
| E54323 | Diagnostic cross-check error            |
| E54324 | Temperature sensor cross-check error    |
| E54325 | Synchronization error detected          |
| E54326 | Overheating error detected              |
| E54327 | Safety judgment result mismatch error   |

---

### 10.3.5 Sequence Diagnosis Errors

| Code   | Meaning                |
|--------|------------------------|
| E54331 | Sequence logic error   |
| E54332 | Sequence bit error     |
| E54333 | Sequence cross-check error |
| E54334 | Sequence timeout error |
| E54335 | Sequence watchdog error|

---

### 10.3.6 Watchdog Errors

| Code   | Meaning                            |
|--------|------------------------------------|
| E54341 | Watchdog timer error               |
| E54342 | Watchdog setting error (ON failure)|

---

### 10.3.7 Version Errors

| Code   | Meaning                         |
|--------|---------------------------------|
| E54350 | Version update failure          |
| E54351 | Firmware cross-check mismatch   |

---

### 10.3.8 FSI Communication Errors

| Code   | Meaning                                |
|--------|----------------------------------------|
| E54450 | FSI sync GPIO timeout error            |
| E54451 | FSI communication error                |
| E54452 | FSI ping test error                    |

---

### 10.3.9 CAN-FD Communication Errors

| Code   | Meaning                                 |
|--------|-----------------------------------------|
| E54500 | CAN communication error with Sensor 1   |
| E54501 | CAN communication error with Sensor 2   |
| E54502 | CAN communication error with Sensor 3   |
| E54503 | CAN communication error with Sensor 4   |
| E54504 | CAN communication ID mismatch error     |

---

### 10.3.10 Sensor Status Errors

| Code   | Meaning                        |
|--------|--------------------------------|
| E54550 | Radar Sensor 1 status error    |
| E54551 | Radar Sensor 2 status error    |
| E54552 | Radar Sensor 3 status error    |
| E54553 | Radar Sensor 4 status error    |

---

### 10.3.11 Sensor Power Errors

| Code   | Meaning                          |
|--------|----------------------------------|
| E54560 | Radar sensor 24V voltage error   |
| E54561 | Radar sensor 5V voltage error    |
| E54562 | Radar sensor 3.3V voltage error  |
| E54563 | Radar sensor 1.8V voltage error  |
| E54564 | Radar sensor 1.2V voltage error  |
| E54565 | Radar sensor 1.0V voltage error  |

---

### 10.3.12 Sensor Overheating Errors

| Code   | Meaning                  |
|--------|--------------------------|
| E54566 | Radar sensor overheating error |

---

### 10.3.13 Sensor Version Errors

| Code   | Meaning                                   |
|--------|-------------------------------------------|
| E54570 | Radar sensor firmware version mismatch    |
| E54571 | Radar sensor firmware cross-check mismatch |
