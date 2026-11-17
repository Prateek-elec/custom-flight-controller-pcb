<div align="center">

# STM32F405 Drone Flight Controller PCB

**A full-featured FPV / UAV flight controller designed from scratch in KiCad 9: F405 MCU, ICM-42688-P IMU, BMP388 barometer, analog OSD, blackbox flash and two onboard switching BECs.**

![KiCad](https://img.shields.io/badge/KiCad-9.0-314CB0?style=for-the-badge&logo=kicad&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-F405RGT6-03234B?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![Status](https://img.shields.io/badge/status-layout%20complete-f59e0b?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-22c55e?style=for-the-badge)

<img src="docs/images/3d-top.png" width="48%" alt="3D render, top side"/> <img src="docs/images/3d-bottom.png" width="48%" alt="3D render, bottom side"/>

</div>

---

## Why this board

Most hobby flight controllers are black boxes. This one is fully open: every net, footprint and power rail is in the KiCad source, so you can study how a modern F405-class FC is put together, or fork it into your own design.

## Hardware at a glance

| Block | Part | Notes |
|---|---|---|
| MCU | **STM32F405RGT6** | 168 MHz Cortex-M4F, the classic Betaflight / ArduPilot / INAV target class |
| IMU | **ICM-42688-P** | 6-axis gyro + accel on SPI |
| Barometer | **BMP388** | I²C, for altitude hold |
| Blackbox | **W25Q128** | 16 MB SPI flash for flight logs |
| OSD | **MAX7456** | Analog video overlay (video in / video out pads) |
| 5 V BEC | **TPS54302** buck | 5 V / 2 A rail for the FC, receiver and peripherals |
| VTX BEC | **TPS54302** buck | Separate switchable rail for the video transmitter / camera (9 V pads) |
| 3.3 V | **AP2112K-3.3** LDO | Clean rail for MCU and sensors |
| Protection | **AO3401A** P-MOSFET + fuse | Reverse-polarity protection on the battery input |
| USB | USB-C | Configuration and firmware flashing |
| Extras | Buzzer driver, status LEDs, boot button, battery voltage + current sense | |

### Connectivity

- **ESC connector**: battery, current sense, telemetry and 4× motor outputs (M1–M4)
- **HD VTX connector**: power + UART for digital video systems
- **Analog VTX / camera pads** routed through the MAX7456 OSD
- **Multiple UARTs** broken out for receiver, GPS, telemetry and VTX control
- I²C pads for an external compass or sensors

## Design files

<table>
<tr>
<td width="50%"><img src="docs/images/schematic.png" alt="Schematic"/><br/><sub><b>Schematic</b>: <code>hardware/kicad/fc002.kicad_sch</code></sub></td>
<td width="50%"><img src="docs/images/pcb-layout.png" alt="PCB layout"/><br/><sub><b>PCB layout</b>: <code>hardware/kicad/fc002.kicad_pcb</code></sub></td>
</tr>
</table>

## Open it yourself

1. Install [KiCad 9](https://www.kicad.org/download/).
2. Clone the repo:
   ```bash
   git clone https://github.com/Prateek-elec/custom-flight-controller-pcb.git
   ```
3. Open `hardware/kicad/fc002.kicad_pro`.
4. To manufacture, open the PCB editor and use **File → Fabrication Outputs → Gerbers** plus **Drill Files**.

## Repository layout

```text
hardware/kicad/   KiCad project (.kicad_pro / .kicad_sch / .kicad_pcb)
docs/images/      Schematic, layout and 3D renders used in this README
```

## Roadmap

- [x] Schematic
- [x] PCB layout and routing
- [ ] Fabrication outputs (Gerbers, BOM, pick-and-place) committed to the repo
- [ ] Board bring-up and test report
- [ ] Betaflight / ArduPilot target configuration
- [ ] Flight testing

## Contributing

Spotted a layout issue or want to suggest a part swap? [Open an issue](https://github.com/Prateek-elec/custom-flight-controller-pcb/issues). Reviews from other FC designers are very welcome.

## License

[MIT](LICENSE) © Prateek Sarkar

<div align="center">

**If this helped you understand flight-controller hardware, a ⭐ helps other builders find it.**

</div>
