# Power Supply
A dual-rail bench power supply: barrel-jack DC input, switched, stepped down to two regulated outputs, 5V and ~3.3V. Designed in KiCad 9.

<img width="1288" height="717" alt="image" src="https://github.com/user-attachments/assets/b43e00df-071b-4722-a19c-64074b60ba27" />

## Overview

Power comes in through a barrel jack, passes through a slide switch for on/off control, and feeds two independent linear regulator stages:

- An **LM7805** for a fixed **5V** rail
- An **LM317**, set via a resistor divider for an adjustable rail configured to output roughly **3.3V**

An LED indicates power status on the LM317 stage. Both rails are broken out to screw terminals and pin headers for flexible use on a bench or in another project.

## Features

- Barrel jack DC input with slide-switch power control
- **5V fixed rail** (LM7805)
- **~3.3V rail** (LM317 + R2/R3 divider, R2 = 330Ω, R3 = 560Ω)
- LED power indicator
- Output broken out via screw terminals (J5, J7) and 3-pin headers (J3, J4)
- Fully open hardware — schematic, PCB layout, and Gerbers included

## Hardware

| Component | Designator | Notes |
|---|---|---|
| Input | J6 | Barrel jack with switch contact |
| Power switch | S1 | Slide switch, in series with input |
| 5V regulator | U1 | LM7805 (TO-220) |
| Adjustable regulator | U2 | LM317 (TO-220), set for ~3.3V |
| Voltage-set resistors | R2, R3 | 330Ω / 560Ω divider on the LM317 ADJ pin |
| LED resistor | R1 | Current limit for power LED |
| Power indicator | D1 | LED |
| Input/output caps | C1, C2, C3 | Bypass/filter capacitors |
| Output terminals | J5, J7 | Screw terminals |
| Output headers | J3, J4 | 3-pin breakout headers |

## Repo Structure

```
Power Supply/
├── Power_Supply.kicad_pro       # KiCad project file
├── Power_Supply.kicad_sch       # Schematic
├── Power_Supply.kicad_pcb       # PCB layout
└── manufacturing/
    ├── Power_Supply-job.gbrjob
    ├── Power_Supply-Edge_Cuts.gbr
    ├── Power_Supply-B_Cu.gbr
    ├── Power_Supply-B_Mask.gbr
    ├── Power_Supply-B_Paste.gbr
    ├── Power_Supply-B_Silkscreen.gbr
    ├── Power_Supply-F_Cu.gbr
    ├── Power_Supply-F_Mask.gbr
    ├── Power_Supply-F_Paste.gbr
    ├── Power_Supply-F_Silkscreen.gbr
    └── drill files 
```
