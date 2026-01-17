# Custom Drone Flight Controller PCB (KiCad)

A custom-designed drone flight controller PCB built for UAV / robotics applications.
This repository contains schematic + PCB layout designed in **KiCad**, along with documentation and renders.

---

## 🔥 Highlights
- Custom Flight Controller PCB (compact layout)
- Designed for UAV multirotor / robotics use cases
- Includes power regulation, sensor interfaces, and IO headers
- Designed for debugging + expandability

---

## 🧩 Major Blocks (Hardware Architecture)
### ✅ MCU / Processing
- STM32-based microcontroller (flight control core)
- Clocking + reset/boot support

### ✅ Sensors
- IMU interface for attitude estimation (gyro + accel)
- Additional I2C/SPI expansion for future sensors

### ✅ Power System
- Multiple regulated rails for clean operation
- USB/VBUS support
- Protection + filtering for stable power delivery

### ✅ IO / Connectivity
- Motor/ESC outputs (PWM)
- UART ports for telemetry / GPS / RC
- I2C / SPI headers for peripherals
- Status LEDs for debugging/health indication

---

## 🖼️ PCB Preview

### 3D View
![3D Render](docs/images/pcb-3d-top.png)

### Schematic
![Schematic](docs/images/schematic.png)

---

## 📂 Repository Structure
- `hardware/kicad/` → KiCad source project files
- `docs/images/` → PCB renders & schematic snapshots
- `fabrication/` → Gerbers, drill files, BOM, pick & place
- `firmware/` → Placeholder for future flight firmware integration

---

## 🛠️ Tools Used
- KiCad (Schematic + PCB + 3D viewer)
- Standard PCB manufacturing flow (Gerber + drill export)

---

## ✅ Project Status
- [x] Schematic completed
- [x] PCB layout completed
- [ ] Full firmware integration (planned)
- [ ] Flight testing & tuning (planned / in-progress)

---

## ⚡ Notes
This is a custom hardware project made for learning, experimentation and UAV development.
You can reuse the structure for educational purposes.

---

## 📌 Author
**Prateek Sarkar**  
UAV Systems | Embedded | PCB Design | Robotics
