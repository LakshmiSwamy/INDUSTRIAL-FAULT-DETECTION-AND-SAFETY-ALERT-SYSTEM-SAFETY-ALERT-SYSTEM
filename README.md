# INDUSTRIAL-FAULT-DETECTION-AND-SAFETY-ALERT-SYSTEM-SAFETY-ALERT-SYSTEM
# 🏭 INDUSGUARD - Industrial Fault Detection and Safety Alert System 🚨

![Embedded Systems](https://img.shields.io/badge/Embedded%20Systems-LPC2148-blue)
![Language](https://img.shields.io/badge/Language-Embedded%20C-green)
![Platform](https://img.shields.io/badge/Platform-ARM7-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Overview

**INDUSGUARD** is an intelligent industrial monitoring and safety system developed using **LPC2148 (ARM7)**. The system continuously monitors **temperature and humidity**, detects abnormal conditions, and sends alert notifications via **GSM SMS** to ensure industrial safety and prevent equipment failures.

The system also allows remote configuration through SMS commands and local configuration using a keypad with password protection.

---

## ✨ Features

✅ Real-time Temperature Monitoring 🌡️  
✅ Humidity Monitoring 💧  
✅ Fault Detection and Alert System 🚨  
✅ SMS Notifications using GSM Module 📱  
✅ Password Protected Access 🔐  
✅ Remote Configuration through SMS 📩  
✅ Local Configuration using Keypad ⌨️  
✅ EEPROM Data Storage 💾  
✅ RTC Timestamp Support ⏰  
✅ LED/Buzzer Fault Indication 🔴  
✅ User Authentication and Security 🛡️

---

## 🛠 Hardware Requirements

| Component | Description |
|------------|-------------|
| 🔹 LPC2148 | ARM7 Microcontroller |
| 🔹 LCD | 16x2 Display |
| 🔹 DHT11 | Temperature & Humidity Sensor |
| 🔹 AT24C256 | EEPROM Memory |
| 🔹 GSM Module (M660A) | SMS Communication |
| 🔹 4×4 Matrix Keypad | User Input |
| 🔹 LEDs | Status Indication |
| 🔹 Switch | External Interrupt |
| 🔹 DB9 Cable / USB-UART | Serial Communication |

---

## 💻 Software Requirements

- 🖥 Keil µVision
- ⚙ Embedded C
- 🔥 Flash Magic
- 📟 Hyper Terminal

---

## 🧩 System Architecture

```
             +-------------+
             |   DHT11      |
             +-------------+
                    |
                    v
             +-------------+
             |   LPC2148    |
             +-------------+
              |     |      |
      --------      |      --------
      |             |             |
      v             v             v
 +---------+   +----------+   +--------+
 | EEPROM  |   | GSM M660A|   |  LCD   |
 +---------+   +----------+   +--------+
      |                          |
      |                          |
      v                          v
 Password Storage          Display Values
      |
      v
 +-------------+
 |  Keypad 4x4 |
 +-------------+
```

---

## ⚙ Working Principle

### 🌡 Sensor Monitoring

- Reads temperature and humidity using **DHT11**.
- Displays current values on LCD.
- Compares current values with preset thresholds stored in EEPROM.

### 🚨 Fault Detection

When sensor values exceed threshold values:

- Red LED/Buzzer turns ON 🔴
- Fault message is generated 📩
- SMS alert is sent to authorized user 📱
- Timestamp is obtained from RTC ⏰

---

## 📲 Remote Control Using SMS

Users can remotely control the system using SMS commands.

### 🔥 Change Temperature Set Point

```
0786T38$
```

Example:

Set temperature threshold to **38°C**

---

### 📞 Change Mobile Number

```
0786M9866666699$
```

Updates the alert receiver number.

---

### 📊 Request Sensor Information

```
0786I$
```

Returns current temperature and humidity values.

---

## 🔐 Security Features

- Password Protected Access 🔑
- EEPROM stores password securely 💾
- Accepts commands only from authorized numbers 📱
- Wrong password indication via buzzer 🔔
- System blocks after three incorrect attempts 🚫

---

## 📁 Project Structure

```
INDUSGUARD
│
├── project_main.c
├── lcd.c
├── lcd.h
├── delay.c
├── delay.h
├── keypad.c
├── keypad.h
├── adc.c
├── adc.h
├── uart.c
├── uart.h
├── i2c.c
├── i2c.h
├── rtc.c
├── rtc.h
├── gsm.c
├── gsm.h
├── dht11.c
├── dht11.h
└── README.md
```

---

## 🚀 Modules Implemented

### 📺 LCD Interface
- Character display
- String display
- Integer display

### ⌨ Keypad Interface
- Password input
- Set point modification

### 📡 UART Communication
- GSM communication
- Interrupt-based transmission

### 💾 EEPROM Interface
- Byte Write
- Byte Read
- Page Write
- Sequential Read

### 🌡 DHT11 Driver
- Temperature sensing
- Humidity sensing

### 📱 GSM Module
- SMS transmission
- SMS reception
- Command processing

### ⏰ RTC
- Timestamp generation

---

## 🔄 Workflow

```text
Start
  ↓
Initialize Peripherals
  ↓
Read Temperature & Humidity
  ↓
Display on LCD
  ↓
Compare with Threshold Values
  ↓
Fault Detected?
  ↓
YES
  ↓
LED/Buzzer ON
  ↓
Send SMS Alert
  ↓
Receive SMS Commands
  ↓
Update EEPROM Parameters
  ↓
Continue Monitoring
```

---

## 🎯 Applications

🏭 Industrial Automation  
⚙ Manufacturing Plants  
🔥 Boiler Monitoring Systems  
🌡 Temperature Control Systems  
💧 Humidity Monitoring Systems  
🚨 Safety and Alarm Systems  
🏢 Smart Factory Solutions

---

## 📚 Technologies Used

- Embedded C 💻
- ARM7 LPC2148 ⚡
- UART Communication 📡
- I2C Protocol 🔄
- EEPROM Memory 💾
- GSM Communication 📱
- RTC ⏰
- Sensor Interfacing 🌡

---

## 👨‍💻 Author
## SWAMI
🎓 Electronics and Communication Engineering (ECE)

### Skills
- Embedded C ⚡
- ARM7 LPC2148 🚀
- Embedded Systems 🔧
- UART, I2C Protocols 📡
- Sensor Interfacing 🌡

---

## ⭐ Future Enhancements

- 📶 IoT Cloud Integration
- 🌐 Wi-Fi Monitoring
- 📱 Mobile Application Support
- 📊 Web Dashboard
- ☁ Data Logging and Analytics
- 🔔 Push Notifications

---

## 📜 License

This project is developed for **educational and industrial safety applications**.

---

# 🌟 If you found this project useful, don't forget to ⭐ star the repository!
