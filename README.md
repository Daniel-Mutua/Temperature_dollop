[README_Temperature_Distance_System.md](https://github.com/user-attachments/files/24324655/README_Temperature_Distance_System.md)
# Temperature and Distance Monitoring System (Arduino)

## Overview
This Arduino project combines **temperature monitoring** using a **DHT11 sensor** and **distance detection** using an **ultrasonic sensor (HC-SR04)**.  
Based on sensor readings, the system automatically controls **two relays**, activates a **buzzer**, and turns on an **LED** for alerts.

The project is suitable for:
- Smart agriculture systems  
- Safety and intrusion detection  
- Automatic temperature-controlled devices  

---

## Components Used
- Arduino Uno (or compatible board)
- DHT11 Temperature Sensor
- HC-SR04 Ultrasonic Sensor
- 2 × Relay Modules
- Buzzer
- LED
- Resistors and Jumper Wires
- Breadboard

---

## Pin Configuration

### Temperature Control
| Component | Arduino Pin |
|---------|------------|
| DHT11 Data | Pin 9 |
| Temperature Relay | Pin 5 |

### Distance Detection
| Component | Arduino Pin |
|---------|------------|
| Ultrasonic Trig | Pin 11 |
| Ultrasonic Echo | Pin 10 |
| Distance Relay | Pin 6 |
| Buzzer | Pin 12 |
| LED | Pin 13 |

---

## Threshold Values
- **Temperature Threshold:** 25 °C  
- **Safety Distance:** 5 cm  

These values can be modified in the code:
```cpp
#define TEMP_THRESHOLD 25
#define SAFETY_DISTANCE 5
```

---

## How the System Works

### 1. Temperature Monitoring
- The DHT11 sensor reads ambient temperature.
- If temperature **exceeds 25°C**, the temperature relay is activated.
- If temperature is normal, the relay remains OFF.
- Temperature readings are displayed on the Serial Monitor.

### 2. Distance Detection
- The ultrasonic sensor measures the distance to an object.
- If an object is detected within **5 cm**:
  - Buzzer turns ON
  - LED turns ON
  - Distance relay is activated
- If no object is detected:
  - All alerts are turned OFF

---

## Required Libraries
Install the following Arduino library:
- **DHT Sensor Library** by Adafruit

Installation:
1. Open Arduino IDE  
2. Go to **Sketch → Include Library → Manage Libraries**  
3. Search for **DHT sensor library**  
4. Install it  

---

## Serial Monitor Output
The Serial Monitor displays:
- Current temperature in °C
- Measured distance in cm
- Error message if DHT sensor fails

Set baud rate to:
```
9600
```

---

## Upload Instructions
1. Connect your Arduino to the computer
2. Open Arduino IDE
3. Paste the provided code
4. Select correct **Board** and **Port**
5. Click **Upload**

---

## Applications
- Greenhouse temperature automation
- Smart home safety alerts
- Object proximity alarms
- Industrial automation

---

## License
This project is for educational and academic use.
