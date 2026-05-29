# 🎟️ Dual Booth Token Management System with Emergency Queue

An **ATmega32-based embedded queue management system** designed to automate customer token handling for service-oriented environments such as hospitals, banks, government offices, and university service desks.

This system supports **dual service booths**, **emergency token prioritization**, **real-time LCD monitoring**, **7-segment token display**, and **audible buzzer alerts** for seamless and fair queue management.

---

## 📌 Project Overview

Traditional queue management often causes confusion, long waiting times, and unfair prioritization. This project introduces a **smart token management system** that automates customer flow using an **ATmega32 microcontroller**.

The system:

* Generates **regular customer tokens**
* Supports **emergency priority tokens**
* Manages **two independent service booths**
* Displays token information on **7-segment displays**
* Shows real-time status on a **16×2 LCD**
* Provides **audible notifications using a buzzer**

Designed as a **low-cost and scalable embedded solution**, this system is ideal for small-to-medium service facilities.

---

## ✨ Features

### 🎫 Smart Token Generation

* Automatic generation of **regular tokens (01–99)**
* Token counter overflow handling (wraps to `01` after `99`)

### 🚨 Emergency Queue System

* Dedicated **priority emergency tokens**
* Emergency tokens are served **before regular customers**
* Supports up to **10 simultaneous emergency requests**

### 🏢 Dual Booth Management

* Two independent booths for customer servicing
* Booth-specific token display
* Real-time synchronization between booths

### 📟 Display System

* **Two dual-digit multiplexed 7-segment displays**
* **16×2 LCD interface** for:

  * Booth status
  * Current token
  * Emergency status
  * Queue information

### 🔔 Audible Notification

* 2-second buzzer alert for every token call
* Double beep for emergency calls

### ⚡ Efficient Embedded Design

* High-frequency multiplexing
* Non-blocking buzzer implementation
* Software debouncing for buttons
* Optimized pin usage

---

## 🛠 Hardware Components

| Component           | Specification                |
| ------------------- | ---------------------------- |
| Microcontroller     | ATmega32                     |
| Display             | 7-Segment Display (4 digits) |
| LCD                 | 16×2 HD44780 LCD             |
| Buzzer              | Active Buzzer                |
| Buttons             | 4 Push Buttons               |
| Resistors           | 330Ω, 10kΩ                   |
| Potentiometer       | 10kΩ                         |
| Power Supply        | 5V DC                        |
| Simulation Software | Proteus 8                    |
| IDE                 | CodeVisionAVR                |

---

## 🔌 System Architecture

### Input System

The system uses push buttons for:

| Button | Function           |
| ------ | ------------------ |
| PD0    | Generate New Token |
| PD1    | Serve Booth 1      |
| PD2    | Serve Booth 2      |
| PD3    | Emergency Queue    |

### Output System

* **7-Segment Displays** → Show active booth token number
* **16×2 LCD** → Shows booth status and token information
* **Buzzer** → Audio alert for token call

---

## 🧠 Working Principle

1. A customer token is generated using the **New Token button**.
2. The token is added to the queue.
3. When Booth 1 or Booth 2 presses the next button:

   * Emergency queue is checked first.
   * If an emergency exists → priority token served.
   * Else → next regular token served.
4. LCD and displays update instantly.
5. A buzzer sounds to notify customers.

---

## ⚙️ Technical Specifications

| Parameter        | Value                      |
| ---------------- | -------------------------- |
| MCU Clock        | 16 MHz                     |
| Voltage          | 5V DC                      |
| Token Range      | 01–99                      |
| Emergency Tokens | E1–E9                      |
| Refresh Rate     | ~320 Hz                    |
| LCD Mode         | 4-bit                      |
| Buzzer Duration  | ~2 Seconds                 |
| Display Type     | Multiplexed Common Cathode |

---

## 📍 Pin Configuration

### PORT A

| Pin     | Function                  |
| ------- | ------------------------- |
| PA0–PA3 | 7-segment digit selection |
| PA7     | Buzzer                    |

### PORT B

| Pin     | Function      |
| ------- | ------------- |
| PB0     | LCD RS        |
| PB1     | LCD Enable    |
| PB4–PB7 | LCD Data Pins |

### PORT C

| Pin     | Function                  |
| ------- | ------------------------- |
| PC0–PC6 | 7-segment segment control |

### PORT D

| Pin | Function         |
| --- | ---------------- |
| PD0 | Token Button     |
| PD1 | Booth 1          |
| PD2 | Booth 2          |
| PD3 | Emergency Button |

---

## 🧪 Simulation & Testing

The system was tested in **Proteus** under multiple scenarios:

✅ Regular token generation
✅ Emergency priority servicing
✅ Dual booth synchronization
✅ Buzzer timing validation
✅ Queue overflow handling
✅ LCD status update testing

### Results Summary

| Test              | Status |
| ----------------- | ------ |
| Token Generation  | ✅ Pass |
| Booth 1 Service   | ✅ Pass |
| Booth 2 Service   | ✅ Pass |
| Emergency Queue   | ✅ Pass |
| Overflow Handling | ✅ Pass |
| Buzzer Timing     | ✅ Pass |

---

## 📂 Project Structure

```plaintext
├── Code/
│   ├── main.c
│   ├── lcd.h
│   ├── lcd.c
│
├── Simulation/
│   ├── TokenSystem.pdsprj
│   ├── TokenSystem.hex
│
├── Circuit Diagram/
│   ├── Circuit.png
│
├── Hardware Images/
│   ├── setup.jpg
│   ├── working.jpg
│
├── Report/
│   ├── EEE373L_Project_Report.pdf
│
└── README.md
```

---

## 🚀 How to Run the Project

### Method 1: Proteus Simulation

1. Open the `.pdsprj` file in **Proteus**
2. Load the generated `.hex` file into the ATmega32
3. Run the simulation
4. Press buttons to test token generation and booth servicing

---

## 🔥 How to Generate `.HEX` File from Code (CodeVisionAVR)

### Step 1: Open Project

Open your project in **CodeVisionAVR**.

### Step 2: Build Project

Go to:

```plaintext
Project → Build All
```

or press:

```plaintext
F9
```

---

### Step 3: Locate Generated HEX File

After successful compilation, CodeVisionAVR automatically generates:

```plaintext
project_name.hex
```

Usually located inside:

```plaintext
ProjectFolder/EXE/
```

or

```plaintext
ProjectFolder/Debug/
```

depending on your configuration.

---

### Step 4: Load HEX in Proteus

1. Double click on **ATmega32**
2. Browse to:

```plaintext
project_name.hex
```

3. Set Clock Frequency:

```plaintext
16 MHz
```

4. Run simulation ▶️



## 🌍 Applications

* 🏥 Hospitals & Clinics
* 🏦 Banks & Financial Institutions
* 🏢 Government Offices
* 🎓 Universities & Service Centers
* 🛍 Retail Service Counters

---

## ⚠️ Limitations

* Emergency token limited to `E1–E9`
* LCD update may introduce slight display delay
* Requires stable 5V supply

---

## 🔮 Future Improvements

* Interrupt-driven architecture
* Wireless remote displays (ESP32)
* Voice announcement system
* More booth scalability
* Touchscreen interface

---

## 👥 Team Members

**Group 04 – EEE373L Embedded System Design Laboratory**

* **Jarin Tarannum Anan**
* **Md Shafinur Islam** 
* **Elma Eleyha** 

---

## 📚 References

1. Queue Management System using AVR Microcontroller
2. LCD Interfacing with Embedded Systems
3. Priority-Based Embedded Queue Scheduling
4. Industrial Embedded Monitoring Systems

---

## 📜 License

This project is developed for **academic and educational purposes** under **EEE373L – Embedded System Design Laboratory**.
