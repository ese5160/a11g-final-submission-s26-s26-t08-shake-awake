[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/Y5lYn2wb)

# A11G Final Submission

**Team Number:** 8

**Team Name:** Shake Awake

**GitHub Repository URL:** [https://github.com/ese5160/final-project-firmware-s26-t08-shake-awake](https://github.com/ese5160/final-project-firmware-s26-t08-shake-awake)

| Team Member Name  | Email Address          | GitHub Handle |
| ----------------- | ---------------------- | ------------- |
| William Hatfield  | hatwill@seas.upenn.edu | whatfield     |
| Christian Durante | cgd2@seas.upenn.edu    | Chris-Durante |

## 1. Video Presentation

[https://youtu.be/FDqjJD4r2T0](https://youtu.be/FDqjJD4r2T0)

## 2. Project Summary

### Device Description

### Device Functionality

### Challenges

### Prototype Learning

### Next Steps and Takeaways

### Project Links

## 3. Hardware and Software Requirements

### 3.1 Hardware Requirements Specification (HRS)

| ID     | Description                                                                                                                                                  |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| HRS-01 | A 6-axis IMU shall be used for movement detection. It should detect when the user has stood up and started walking.                                          |
| HRS-02 | A speaker be used to make a noise of at least 70 dB. The PWM signal used to drive the speaker should be customizable.                                        |
| HRS-03 | An LCD screen can display current time as well as both cloud (weather) and local (temperature, light sensors) environmental data                             |
| HRS-04 | The 917 MCU should be used as the sole microcontroller.                                                                                                      |
| HRS-05 | The device shall use a single-cell, 3.7 V, 2200mAh Lithium ion battery                                                                                       |
| HRS-06 | The device should have a battery life of at least 8  hours.                                                                                                  |
| HRS-07 | The device should have at least two buttons that directly toggle the settings of the clock (offline configuration of clock and alarm time, dark/light mode). |
| HRS-08 | The device should gather additional environmental data in real time with temperature and light sensors                                                       |

### 3.2 HRS Evaluation

| ID     | HRS Goal             | Success    | Measurement / Discussion                                                                             |
| ------ | -------------------- | ---------- | ---------------------------------------------------------------------------------------------------- |
| HRS-01 | Movement Detection   | Complete   | Refer to used[dev boards datasheet](https://cdn.sparkfun.com/assets/c/f/9/d/1/lsm6dso_datasheet.pdf)    |
| HRS-02 | Speaker Noise        | Partial    | Speaker noise measured to be from 1m away, is not customizable.                                      |
| HRS-03 | LCD Screen           | Complete   | Display updates in real time to show new time or alarm timings sent from the cloud                   |
| HRS-04 | MCU Choice           | Complete   | Existential, no additional controllers or processor dev boards used                                  |
| HRS-05 | Battery Choice       | Complete   | Existential, case work modelled around this particular battery pack shape                            |
| HRS-06 | Battery Life         | Complete   | Typcial current usage of 122.89 mA provides an expected battery life of 17.9 hrs, 223% of target    |
| HRS-07 | Button Configuration | Incomplete | Node-RED functionality deemed faster and more crtical, keypad integration generally is a future step |
| HRS-08 | Environmental Data   | Complete   | See Node-RED dashboard (video demonstration)                                                         |

### 3.2 Software Requirements Specification (SRS)

| ID     | Description                                                                                                                                            |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SRS-01 | The IMU 3-axis acceleration and gyroscope data shall be measured with 16-bit depth every 100 milliseconds +/-10 milliseconds.                          |
| SRS-02 | The IMU shall be controlled via I2C communication                                                                                                      |
| SRS-03 | The software shall store activity data (time to turn off, temperature, ambient light) to display on-device, and to send to the cloud                   |
| SRS-04 | The software shall be designed with and controlled by FreeRTOS in order to achieve consistent operation and extensibility of the code base.            |
| SRS-05 | The software will update the display according to a series of nested state-machines, allowing users to control various menus with a keypad or buttons. |
| SRS-06 | The software tracks local environmental data (temperature, ambient light), and displays it along with the time.                                        |
| SRS-07 | The device should be able to store and play customizable audio files, uploaded directly or wirelessly.                                                 |
| SRS-08 | The software should filter user movements such that noise and simply picking up the device do not turn off the alarm.                                  |

### 3.4 SRS Evaluation

| ID     | HRS Goal               | Success    | Measurement / Discussion                                                                                                |
| ------ | ---------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------- |
| SRS-01 | IMU Polling            | Complete   | Refer to used[dev boards datasheet](https://cdn.sparkfun.com/assets/c/f/9/d/1/lsm6dso_datasheet.pdf), as well as          |
| SRS-02 | IMU Control            | Complete   | Existential, refer to codebase                                                                                          |
| SRS-03 | Edge Computing         | Complete   | Video demonstration shows Node-RED integration                                                                          |
| SRS-04 | RTOS                   | Complete   | Refer to codebase                                                                                                       |
| SRS-05 | Menus (State Machines) | Incomplete | Keypad integration forgone, see Button Configuration                                                                    |
| SRS-06 | Environmental Data     | Partial    | Displayed only on Node-RED, not on-device display                                                                       |
| SRS-07 | Custom Audio           | Incomplete | Custom audio uploads were prohibitively blocking during firmware development, at least within bounds of course timeline |
| SRS-08 | Noise Rejection        | Complete   | Demonstrated in video, code snippet attached                                                                            |

## 4. Project Photos

Final Prototype

![final_prototype](image/README/final_prototype.png)

![final_internal](image/README/final_internal.png)

PCBA, top

![pcba_front](image/README/pcba_front.png)

PCBA, bottom

![pcba_back](image/README/pcba_back.png)

Thermal Performance

![thermal](image/README/thermal.png)

Altium Design 2D

![altium_2d](image/README/altium_2d.png)

Altium Design 3D

![altium_3d](image/README/altium_3d.png)

Node-RED Dashboard

![node_red_dash1](image/README/node_red_dash1.png)

![node_red_dash2](image/README/node_red_dash2.png)

Node-RED Backend

![node_red_back](image/README/node_red_back.png)

Block Diagram

## 5. Codebase

Description of file structure

Locations of Node-Red Dashboard File
