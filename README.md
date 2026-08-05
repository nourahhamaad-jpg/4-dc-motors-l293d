# 🤖 Arduino-Based 4 DC Motor Control with L293D Driver

## 📖 Overview
This project demonstrates how to control a 4-wheel robot setup using an **Arduino Uno** and an **L293D H-Bridge Motor Driver**. The system executes an automated movement sequence: advancing forward, reversing backward, and alternating left/right turns to simulate vehicle steering.

---

## 🎬 Simulation Video & Demo



https://github.com/user-attachments/assets/3bd740d6-b1f2-47ed-b19a-cb3f03f538d3





---

## 🛠️ Hardware Requirements

| Component | Quantity | Role |
| :--- | :---: | :--- |
| **Arduino Uno** | 1 | Processes logic and outputs timing & directional signals |
| **L293D IC** | 1 | Dual H-bridge motor driver supplying voltage/current to motors |
| **DC Motors** | 4 | Actuators representing the 4-wheel drive system |
| **9V Battery** | 1 | External power supply dedicated to driving the motors |
| **Breadboard & Wires** | 1 Set | Interconnecting circuit pins and power rails |

---

## ⚡ Functional Logic
The Arduino microcontroller dictates motion by sending `HIGH` or `LOW` logic signals to the input pins of the L293D driver IC:

1. **Power Separation:** The L293D isolates the low-power Arduino logic circuit from the high-power demand of the 4 DC motors.
2. **Dual-Side Control:** The motors are wired in pairs (Left Side & Right Side). 
   * **Forward Drive:** Both sides spin in the forward direction.
   * **Reverse Drive:** Directional polarity flips on all 4 motors.
   * **Differential Turning:** Alternating clockwise/counter-clockwise states allow sharp right and left turns.

---

## 🔌 Circuit Wiring Matrix

| Source Component | Arduino / Battery Pin | Target L293D Pin | Function |
| :--- | :--- | :--- | :--- |
| **Arduino Uno** | Pin 4 | Input 1 (Pin 2) | Left Motor Direction A |
| **Arduino Uno** | Pin 5 | Input 2 (Pin 7) | Left Motor Direction B |
| **Arduino Uno** | Pin 6 | Input 3 (Pin 10) | Right Motor Direction A |
| **Arduino Uno** | Pin 7 | Input 4 (Pin 15) | Right Motor Direction B |
| **Arduino Uno** | 5V Rail | Pins 1, 9, 16 | Enable 1/2, Enable 3/4 & Logic Vcc1 |
| **Arduino Uno** | GND Rail | Pins 4, 5, 12, 13 | Common Ground Connection |
| **9V Battery** | Positive (+) | Pin 8 | Motor Power Vcc2 |
| **9V Battery** | Negative (-) | Ground Rail | Common Power Ground |

---

## 🔗 Circuit Simulation Link
* **Tinkercad Project:** [View Live Simulation on Tinkercad](https://www.tinkercad.com/things/kOqasIi3Xas/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=CJm3S5CbvRRUoZp_kIXpnTfnKW1g1qknawNdfOy9vVw)
