# 🛸 Autonomous INAV F450 Drone Build

A cost-effective, high-performance autonomous drone built using the **Speedybee F405 Wing Mini** flight controller running **INAV**, an **F450 frame**, and **ExpressLRS (ELRS)** control link. Designed for waypoint navigation, autonomous missions, and reliable long-range telemetry.

---

## 📋 Features

* **Autonomous Flight:** Fully supports waypoint navigation, position hold, and automated Return-to-Home (RTH) via M100-5883 GPS.
* **Long-Range Control:** Rock-solid, low-latency control link using ExpressLRS (ELRS 2.4GHz).
* **Budget-Friendly:** Full component ecosystem optimized for a ~$150 build cost.
* **Versatile Payload:** Integrated payload release mechanism for delivery or drop-test applications.

---

## 🛠️ Parts & Bill of Materials (BOM)

### Drone Parts
* **Frame:** F450 Frame Kit ($20)
* **Motors:** 2212 Motor (1400KV) ($5 each)
* **ESC:** 40A Speed Controller ($5)
* **Propellers:** 8045 / 8x4.5 Propellers ($5)
* **Flight Controller:** Speedybee F405 Wing Mini ($40)
* **Navigation:** M100-5883 GPS Module ($20)
* **Control Link:** ELRS Receiver (2.4GHz) ($10)
* **Payload:** Payload Release Mechanism ($5)
* **Actuator:** MG995 Servo (180 degree) ($5)
* **Battery:** 3S ~5000mAh LiPo Battery ($30)

### Support Equipment & Tools
* **Hardware:** M3 Plastic Standoffs ($5), Thin-head M3 Screws ($5)
* **Charger:** Hota D6 Charger ($90)
* **Soldering & Assembly:** Pinecil Soldering Iron ($40), Magnetic "Helping" Hands ($50), Servo Tester ($5)
* **Radio Transmitters:** RadioMaster Boxer ELRS ($200) *or* RadioMaster Pocket ELRS ($90)

---

## 🔌 Wiring & Pinout Guide

*(Add your wiring diagram or pinout table here as you build out the project)*

| Component | Flight Controller Port (Speedybee F405 Wing Mini) | Notes |
| :--- | :--- | :--- |
| **GPS (M100-5883)** | UART 2 (TX/RX) | Configure UBLOX protocol in INAV Configurator |
| **ELRS Receiver** | UART 1 / CRSF | Serial RX enabled |
| **ESC Signal** | S1 - S4 / PWM outputs | Motor protocol: Dshot or PWM |
| **Payload Servo** | S5 / Servo Output | Mapped to a transmitter switch for release |

---

## ⚙️ Software & INAV Configuration

1. **Flash Firmware:** Flash the Speedybee F405 Wing Mini target with the latest stable version of **INAV**.
2. **Ports Tab:** 
   * Enable **Serial RX** on the UART connected to your ELRS receiver.
   * Set **GPS** on the corresponding UART at `57600` baud (or auto).
3. **Configuration Tab:**
   * Set frame type to Quadcopter X.
   * Enable GPS, Navigation, and Failsafe features.
4. **Modes Tab:**
   * Set up switches for **ANGLE / HORIZON**, **NAV RTH**, **NAV POSHOLD**, and **PAYLOAD RELEASE**.

---

## 🚀 Getting Started

1. Clone this repository or download configuration dumps (`.txt` files for CLI settings).
2. Solder components carefully using a temperature-controlled iron (like the Pinecil).
3. Test all motor directions, failsafes, and GPS lock outdoors before your first maiden flight.

---

## 📜 License
This project is open-source and available under the [MIT License](LICENSE).
