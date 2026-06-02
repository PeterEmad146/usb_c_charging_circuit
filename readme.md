# ⚡ USB-C Power Delivery (PD) Charging Circuit

![Hardware License](https://img.shields.io/badge/Hardware%20License-CERN%20OHL%20S-blue)
![Status](https://img.shields.io/badge/Status-Prototype-orange)
![USB-C](https://img.shields.io/badge/USB--C-Power%20Delivery-green)

A compact, high-efficiency USB-C charging circuit designed to negotiate Power Delivery (PD) protocols and safely charge Lithium-ion battery packs. This project aims to replace legacy barrel jacks with a modern, universal USB-C charging interface.

## ✨ Features

* **USB-C Power Delivery (PD) Support:** Negotiates 5V, 9V, 12V, 15V, or 20V depending on the source capabilities and configuration.
* **High-Efficiency Switching:** Uses a synchronous buck/boost topology to minimize heat dissipation.
* **Battery Protection:** Integrated Over-Voltage Protection (OVP), Over-Current Protection (OCP), and Thermal Shutdown.
* **Charge Status Indicators:** Onboard LEDs to indicate 'Charging', 'Fully Charged', and 'Fault' states.
* **Compact Footprint:** Designed to be easily integrated into existing projects or enclosures.

## 📋 Hardware Specifications

| Specification | Value |
| :--- | :--- |
| **Input Connector** | USB-C Receptacle (16-pin or 24-pin) |
| **Input Voltage Range** | 5V - 20V DC (via USB PD) |
| **Max Charge Current** | ~3.0A (Configurable via resistor) |
| **Supported Chemistries**| 1S - 4S Lithium-Ion / LiPo (Configurable) |
| **Charge Controller IC** | *[Insert specific IC here, e.g., IP2368, BQ25792]* |
| **PD Controller IC** | *[Insert specific IC here, e.g., CH224K, FUSB302]* |
| **Operating Temp** | -10°C to 65°C |

## 📐 Schematic & PCB

*(Replace these with actual renders or links to your EDA project files once completed)*

* **Schematic (PDF):** [`docs/schematic.pdf`](#)
* **Gerber Files:** [`hardware/gerbers/`](#)
* **KiCad/Altium Source:** [`hardware/src/`](#)

## 🛒 Key Bill of Materials (BOM)

| Designator | Component | Description |
| :--- | :--- | :--- |
| **U1** | USB PD Sink Controller | Handles CC1/CC2 negotiation |
| **U2** | Charge Controller IC | Regulates current and voltage to the battery |
| **J1** | USB-C Port | SMD USB-C receptacle |
| **L1** | Inductor | High-current power inductor for switching |
| **C1-C4**| MLCC Capacitors | Decoupling and bulk capacitance (X5R/X7R) |

*For the full interactive BOM, please see `docs/ibom.html`.*

## 🚀 Getting Started

### Prerequisites
* A compatible USB-C PD wall adapter and a certified USB-C cable.
* Appropriate battery pack for your configuration.
* Multimeter for initial voltage verification.

### Assembly & Testing
1. **PCB Assembly:** Solder components according to the BOM. Ensure the thermal pad on the Charge Controller IC is properly soldered to the ground plane for heat dissipation.
2. **Initial Test (Without Battery):**
   * Plug in the USB-C cable.
   * Measure the voltage at the battery terminals using a multimeter. It should match the float voltage of your configured battery chemistry (e.g., 4.2V for 1S Li-ion).
   * Verify that the PD negotiation is working (input voltage should match your target PD profile).
3. **Battery Connection:**
   * **⚠️ DANGER:** Ensure polarity is absolutely correct before connecting the battery.
   * Connect the battery and observe the charge status LEDs.
   * Monitor the temperature of the ICs during the first heavy charge cycle.

## ⚠️ Safety Warning

**Lithium batteries are dangerous if handled improperly.**
* This circuit is designed for educational and prototyping purposes.
* Always double-check your resistor configurations for charge current and voltage limits.
* Never charge a damaged or over-discharged battery.
* Do not leave the board unattended during its first charge cycles.
* Use at your own risk. The author is not responsible for property damage or injury.

## 📄 License

This project is licensed under the CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S). See the `LICENSE` file for details.