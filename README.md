# 🌿 Smart Irrigation System with Adjustable Thresholds

![Circuit Diagram](https://raw.githubusercontent.com/DanielRajChristeen/Smart-Irrigation-System-with-Adjustable-Thresholds/main/Circuit_diagram.jpg)

A fully automated irrigation system that uses soil moisture, temperature, and tank level sensors to monitor environmental conditions and display status through an LCD. This project captures threshold values dynamically at startup and compares live readings to them. Based on the comparison, it triggers alerts and can activate a water pump through a relay. It is suitable for different types of plants, soil, and growing conditions, and is easy to set up using standard Arduino components.

---

## 🌱 Overview

Traditional irrigation often wastes water and requires manual control. This smart irrigation system automates the watering process by continuously measuring soil moisture, ambient temperature, and water tank levels. Instead of relying on pre-programmed values, it intelligently sets thresholds from initial readings at startup. These serve as adaptive baselines, allowing the system to identify when soil becomes too dry, the temperature too high, or the tank too low. The system is designed to be modular, expandable, and efficient, using an LCD to communicate system status clearly and reliably.

---

## 🚀 Features

The project supports dynamic threshold detection by reading the sensor values during the initial boot and storing them as reference points. Real-time values are then constantly compared to these thresholds. If the moisture level drops below its baseline, the LCD displays "Low Moisture." Similarly, alerts for "High Temperature" or "Empty Tank" appear when those values cross their respective limits. An optional relay setup can trigger a water pump, enabling true automation. The display provides up-to-date readings of all three values — moisture, temperature, and tank water level. The system is highly customizable and runs on low power, making it suitable for remote or battery-powered setups.

---

## 🧰 Hardware Requirements

To build this smart irrigation system, the following hardware components are needed:

| Component              | Description                                        |
|------------------------|----------------------------------------------------|
| Arduino UNO / Nano     | Core microcontroller for processing sensor input   |
| Soil Moisture Sensor   | Measures the water content in the soil             |
| Temperature Sensor     | Analog sensor like LM35 to detect ambient heat     |
| Water Level Sensor     | Checks water level in the storage tank             |
| Relay Module           | Controls the pump or solenoid valve                |
| Water Pump / Valve     | Distributes water to plants                        |
| 20x4 LCD Display       | Shows real-time sensor values and status messages  |
| Potentiometer          | Used for adjusting LCD contrast                    |
| Breadboard & Jumpers   | For easy prototyping                               |
| External Power Supply  | For powering pump and Arduino (USB/adapter)        |

---

## 🧑‍💻 Software Requirements

The project is coded using the Arduino IDE and requires no third-party libraries apart from the default `LiquidCrystal.h` for LCD communication. Ensure you have the latest version of the Arduino IDE, which can be downloaded from [the official Arduino website](https://www.arduino.cc/en/software).

---

## 🔌 Circuit Connections

The sensor and component pins are mapped as follows:

| Arduino Pin   | Component             | Function Description               |
|---------------|-----------------------|------------------------------------|
| A0            | Moisture Threshold    | Initial moisture threshold value   |
| A1            | Temperature Threshold | Initial temperature threshold      |
| A2            | Tank Threshold        | Initial tank level threshold       |
| A3            | Moisture Live         | Real-time moisture reading         |
| A4            | Temperature Live      | Real-time temperature reading      |
| A5            | Tank Level Live       | Real-time tank water reading       |
| D2–D7         | LCD 20x4              | Control and data lines             |
| D12           | Relay Module          | Optional pump/valve control        |
| VCC/GND       | All Components        | Power and ground lines             |

> 📷 Refer to the diagram at the top for exact wiring layout.

---

## 🛠️ Getting Started

To begin, first connect all the components as described in the wiring diagram. Then, open the `.ino` file in the Arduino IDE and upload it to your board. During the initial few seconds of operation, the Arduino captures the threshold values from all sensors. These serve as adaptive baselines to identify changes in soil or environmental conditions. The LCD will show messages like "Set Threshold Values" while this process is happening. Afterward, it enters monitoring mode, displaying current values and activating alerts as needed.

---

## ⚙️ How It Works

When powered on, the Arduino reads sensor data from three analog pins and saves them as moisture, temperature, and tank-level thresholds. In the main loop, it reads the live values and compares each to its respective threshold. If soil moisture is below the threshold, it displays a "Low Moisture" alert. If the temperature is too high, it shows "High Temp." If the water tank is too empty, it warns with "Empty Tank." These conditions are displayed clearly on the LCD. Although the relay is included in the circuit, its logic can be easily modified to activate a pump during these warnings, allowing automated irrigation.

---

## 📊 Example Moisture Readings

The values below provide a general reference but can vary depending on sensor model and soil:

| Soil Condition    | Sensor Value (Analog) |
|-------------------|------------------------|
| Dry               | 0–400                  |
| Moist (Ideal)     | 400–600                |
| Wet/Saturated     | 600–1023               |

These values are useful if you prefer to set fixed thresholds manually. However, this system adapts to your specific environment by setting thresholds automatically.

---

## 🧪 Calibration Tips

If you want to manually calibrate thresholds, you can override the default dynamic threshold behavior. To do this, place the moisture sensor into dry soil and note the analog value. Then, place it in fully saturated soil and record that value too. Choose a threshold that best suits the watering needs of your plant, ideally somewhere between the two. Similar calibration can be done for tank sensors and temperature depending on your local climate or application.

---

## 🔄 Future Improvements

This project can be extended in many ways. Adding Wi-Fi or Bluetooth capability would enable remote control and live data monitoring. A web or mobile dashboard could be created to track moisture trends and manually adjust thresholds. Multiple sensors could be integrated to handle separate plant zones. Weather APIs could allow the system to pause irrigation when rain is predicted. SMS or push alerts could notify users when intervention is needed. Logging data to SD cards or cloud storage would also be useful for analysis and long-term tracking.

---

## 🙋‍♂️ Contributing

Contributions are welcome! If you encounter bugs, have suggestions for features, or want to improve the code, feel free to submit an issue or pull request. Collaboration is encouraged, and your input helps improve the system for everyone.

---

## 📄 License

This project is licensed under the **MIT License**, which means you're free to use, modify, and share the project. Just make sure to retain the original license and credits in any derivative work.
