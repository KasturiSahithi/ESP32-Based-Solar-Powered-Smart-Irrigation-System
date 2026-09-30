# ESP32-Based-Solar-Powered-Smart-Irrigation-System
A solar-powered smart irrigation system using ESP32 and multiple sensors to automate irrigation based on real-time soil and environmental conditions, helping reduce water wastage and manual effort in agriculture.


## 📌 Project Overview

This project presents a **solar-powered adaptive smart irrigation system** designed to provide efficient and automated irrigation for sustainable agriculture, particularly in rural and remote areas.

The system uses an **ESP32 microcontroller** to collect real-time data from multiple sensors and automatically control irrigation based on soil and environmental conditions. Unlike conventional irrigation systems that depend only on a fixed soil-moisture threshold, the proposed system considers **soil moisture, temperature, humidity, and light intensity** for adaptive irrigation decisions.

The system also incorporates **intelligent fault diagnosis and pump protection** to identify abnormal conditions such as pump failure, dry-run conditions, sensor malfunction, low battery, and an empty water tank.

Sensor and operational data are uploaded to a **cloud dashboard** for real-time monitoring and historical analysis.

---

## 🎯 Objectives

- Design and develop a solar-powered smart irrigation system using ESP32.
- Implement adaptive irrigation using soil moisture, temperature, humidity, and light intensity.
- Develop an intelligent fault diagnosis mechanism for detecting system abnormalities.
- Implement smart pump protection during abnormal operating conditions.
- Monitor water consumption, battery status, solar energy generation, and pump operating hours.
- Upload real-time sensor and analytical data to a cloud dashboard.
- Improve water-use efficiency, reduce energy wastage, and enhance system reliability.

---

## 🏗️ System Architecture

```text
                    ☀️ SOLAR PANEL
                          │
                          ▼
                 🔋 CHARGE CONTROLLER
                          │
                          ▼
                    🔋 BATTERY
                          │
                          ▼
                    ⚡ ESP32
                          │
          ┌───────────────┼────────────────┐
          │               │                │
          ▼               ▼                ▼
   🌱 Soil Moisture   🌡️ DHT11/DHT22    ☀️ LDR
      Sensors          Temperature &      Light
       (Zones)           Humidity        Intensity
          │               │                │
          └───────────────┼────────────────┘
                          │
                 ┌────────┴────────┐
                 │                 │
                 ▼                 ▼
          💧 Water Flow      🚰 Tank Level
             Sensor             Sensor
                 │                 │
                 └────────┬────────┘
                          │
                          ▼
                 🧠 Adaptive Decision
                       Logic
                          │
              ┌───────────┴───────────┐
              │                       │
              ▼                       ▼
        🛡️ Fault Diagnosis      💧 Pump Control
              │                       │
              ▼                       ▼
        Pump Protection        Relay/MOSFET
                                      │
                                      ▼
                                💦 Water Pump
                                      │
                                      ▼
                              🌱 Irrigation Zones

                          │
                          ▼
                    📺 LCD Display
                          │
                          ▼
                    ☁️ Cloud Dashboard
````

---

## 🔧 Hardware Components

| Component                            | Purpose                                     |
| ------------------------------------ | ------------------------------------------- |
| **ESP32**                            | Main controller and Wi-Fi communication     |
| **Solar Panel**                      | Renewable power generation                  |
| **Solar Charge Controller**          | Battery charging management                 |
| **12V Battery**                      | Energy storage                              |
| **Capacitive Soil Moisture Sensors** | Monitor soil moisture                       |
| **DHT11/DHT22**                      | Measure temperature and humidity            |
| **LDR Sensor**                       | Measure light intensity                     |
| **Water Flow Sensor**                | Monitor water consumption and flow          |
| **Ultrasonic Water Level Sensor**    | Monitor tank water level                    |
| **Soil pH Sensor**                   | Monitor soil acidity/alkalinity             |
| **Relay/MOSFET Driver**              | Control the water pump                      |
| **DC Water Pump**                    | Irrigation                                  |
| **Solenoid Valves**                  | Control individual irrigation zones         |
| **LCD Display**                      | Display real-time system information        |
| **Voltage/Current Sensor**           | Monitor battery/solar electrical parameters |
| **Buzzer/LEDs**                      | Fault and status indication                 |

---

## ⚙️ Key Features

### 🌱 Adaptive Irrigation

The system considers multiple environmental parameters instead of relying solely on a fixed moisture threshold.

Parameters include:

* Soil moisture
* Temperature
* Humidity
* Light intensity

This enables more responsive irrigation decisions.

---

### 🧠 Intelligent Fault Diagnosis

The system identifies abnormal operating conditions such as:

* Pump failure
* Dry-run condition
* Soil moisture sensor malfunction
* Low battery
* Empty water tank
* Abnormal water flow

---

### 🛡️ Smart Pump Protection

When an abnormal condition is detected, the ESP32 can automatically stop the pump to prevent damage.

The system can also restart irrigation when safe operating conditions are restored.

---

### 💧 Water Management

The system monitors:

* Water flow rate
* Water consumption
* Pump operating duration
* Irrigation status

This helps analyze and improve water-use efficiency.

---

### ☀️ Solar Energy Management

The system uses solar energy as its primary power source and monitors:

* Solar power generation
* Battery voltage
* Battery status
* Energy consumption

---

### ☁️ IoT Monitoring

Sensor and system information is uploaded to a cloud dashboard for:

* Real-time monitoring
* Historical data analysis
* System status monitoring
* Water and energy analysis

---

## 🔄 Working Principle

1. The solar panel generates electrical energy.
2. The charge controller manages charging of the battery.
3. The ESP32 receives power from the battery through the regulated power supply.
4. Sensors continuously collect soil and environmental data.
5. ESP32 processes the sensor readings.
6. The adaptive irrigation logic determines whether irrigation is required.
7. The pump and corresponding irrigation valve are activated when required.
8. Water flow is monitored during irrigation.
9. Fault diagnosis checks for abnormal conditions.
10. The pump is automatically protected during unsafe conditions.
11. Sensor and system data are displayed on the LCD.
12. Data is transmitted to the cloud dashboard for remote monitoring and analysis.

---

## 🚨 Fault Detection Examples

| Condition                | System Response                         |
| ------------------------ | --------------------------------------- |
| Dry soil                 | Start irrigation                        |
| Sufficient soil moisture | Stop irrigation                         |
| Empty water tank         | Stop pump                               |
| Pump ON + no water flow  | Detect possible pump/dry-run fault      |
| Low battery              | Protect/disable pump                    |
| Sensor malfunction       | Generate fault indication               |
| Abnormal flow            | Detect possible blockage/leak condition |

---

## 📊 Parameters Monitored

```text
🌱 Soil Moisture
🌡️ Temperature
💧 Humidity
☀️ Light Intensity
🚰 Water Level
💦 Water Flow
🔋 Battery Voltage
☀️ Solar Energy
⚙️ Pump Status
⏱️ Pump Operating Hours
```

---

## 💻 Technologies Used

* **Microcontroller:** ESP32
* **Programming:** Embedded C/C++ / Arduino IDE
* **Dashboard:** Web-based monitoring dashboard
* **Sensors:** Soil moisture, DHT11/DHT22, LDR, flow, tank level, pH
* **Actuation:** DC pump, relay/MOSFET, solenoid valves
* **Power:** Solar PV + rechargeable battery

---

## 📈 Expected Outcomes

* Automated irrigation based on real-time conditions
* Improved water-use efficiency
* Reduced unnecessary pump operation
* Reduced energy wastage
* Protection against pump dry-run and abnormal conditions
* Continuous monitoring of water and energy parameters
* Remote monitoring through IoT
* Sustainable and low-cost irrigation solution for rural agriculture

---

## 🌍 Sustainable Development Goals

This project contributes to:

* **SDG 2 – Zero Hunger**
* **SDG 6 – Clean Water and Sanitation**
* **SDG 7 – Affordable and Clean Energy**
* **SDG 12 – Responsible Consumption and Production**
* **SDG 13 – Climate Action**

---

## 🔮 Future Enhancements

* AI/ML-based irrigation prediction
* Weather forecast integration
* Mobile application
* Advanced soil nutrient monitoring
* Automated fertigation
* Larger multi-zone agricultural deployment
* Advanced predictive fault diagnosis
* Improved solar energy optimization

---

## 👩‍💻 Project Team

**Project:** Solar-Powered Adaptive Smart Irrigation System
**Controller:** ESP32
**Domain:** IoT | Embedded Systems | Renewable Energy | Smart Agriculture | Automation

---

## ⭐ Project Highlights

> **Sense → Analyze → Diagnose → Protect → Irrigate → Monitor**

The system combines **solar energy, embedded control, adaptive irrigation, intelligent fault diagnosis, pump protection, water/energy monitoring, and IoT connectivity** into a single smart agriculture solution.

---

## 📄 License

This project is developed for **academic and educational purposes**.

```
```
