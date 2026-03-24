# 🚨 Borewell Human Fall Detection & Alert System (STM32 + GSM + Sensors)

## 📌 Overview

This project is an embedded safety system designed to detect human falls inside borewells and immediately send alert messages using GSM communication. It continuously monitors environmental conditions such as distance, temperature, humidity, and gas levels to identify dangerous situations in real time.

The system is built using STM32 microcontroller with multiple sensors and a SIM800 GSM module for emergency communication.

---

## 🚀 Key Features

* Real-time human fall detection using ultrasonic sensor
* Automatic SMS alert system via GSM (SIM800)
* Temperature and humidity monitoring (DHT11)
* Gas leakage detection using analog gas sensor
* Live data display on I2C LCD
* Embedded real-time decision making system
* Fail-safe alert mechanism for emergency rescue

---

## ⚙️ Hardware Components

* STM32 Microcontroller (STM32F103 series)
* Ultrasonic Sensor (Distance Measurement)
* DHT11 Temperature & Humidity Sensor
* Gas Sensor (Analog via ADC)
* SIM800 GSM Module
* 16x2 I2C LCD Display
* Power Supply Unit

---

## 💻 Software & Technologies

* Embedded C (STM32 HAL Library)
* STM32CubeIDE
* UART Communication (GSM)
* I2C Communication (LCD)
* ADC (Gas Sensor Input)
* GPIO (Ultrasonic + DHT11)

---

## 🔌 System Working

### 🟢 1. System Initialization

* Initializes GPIO, ADC, UART, and I2C peripherals
* LCD displays project startup message
* GSM module is tested using AT commands

---

### 📏 2. Distance Measurement (Ultrasonic Sensor)

* Trigger pulse is sent from STM32
* Echo signal duration is measured
* Distance is calculated using time-of-flight principle

👉 Used to detect human presence/fall inside borewell

---

### 🌡️ 3. Temperature & Humidity (DHT11)

* Custom bit-level protocol implemented
* Reads temperature and humidity values
* Displays values on LCD

---

### ☣️ 4. Gas Detection (ADC)

* Analog gas sensor connected to ADC channel
* Reads environmental gas concentration
* Helps detect toxic conditions

---

### 📟 5. LCD Display (I2C)

Displays real-time data:

* Temperature (°C)
* Humidity (%)
* Distance (cm)
* Gas level

---

### 🚨 6. Fall Detection Logic

* If distance < 30 cm:

  * System assumes a fall has occurred
  * Displays **"FALL DETECTED"** on LCD
  * Triggers SMS alert

---

### 📡 7. GSM Alert System (SIM800)

* Sends AT commands via UART
* Configures SMS text mode
* Sends emergency alert message with sensor data

Example SMS:

```
BOREWELL ALERT
Temp: 28C
Hum: 65%
Dist: 25.3cm
Gas: 320
```

---

### 🔁 8. Continuous Monitoring Loop

* Checks trigger input pin
* Continuously reads all sensors
* Updates LCD in real-time
* Sends alert when threshold condition is met

---

## 📡 Communication Interfaces Used

| Interface | Purpose                    |
| --------- | -------------------------- |
| UART      | GSM (SIM800 communication) |
| I2C       | LCD Display                |
| ADC       | Gas Sensor                 |
| GPIO      | Ultrasonic + DHT11         |

---

## 🌐 Applications

* Borewell rescue systems
* Underground safety monitoring
* Industrial confined space monitoring
* Disaster management systems
* Smart safety IoT systems

---

## 🔮 Future Enhancements

* Add GPS tracking for location sharing
* Integrate camera for visual monitoring
* Cloud connectivity (IoT dashboard)
* AI-based fall confirmation system
* Battery backup and low-power optimization

---

## 🧠 Technical Highlights

* Direct GPIO control for timing-sensitive DHT11 communication
* Custom ultrasonic timing logic without timers
* UART-based GSM AT command handling
* Real-time multi-sensor integration
* Embedded decision-making system

---

## 👨‍💻 Author

Sowgandh S
Embedded Systems & AI–IoT Developer
GitHub: https://github.com/kingstonsow45
