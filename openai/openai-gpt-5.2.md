# openai/gpt-5.2

GPT-5.2 is the latest frontier-grade model in the GPT-5 series, offering stronger agentic and long context perfomance compared to GPT-5.1.

## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [x] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|   GND  |  GND   |B1  (24) 
A11| SSRXp2 | SSRXp1 |B2  (23)
A10| SSRXn2 | SSRXn1 |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|  SBU1  |  CC2   |B5  (20)
 A7|    D-  |  D+    |B6  (19)
 A6|    D+  |  D-    |B7  (18)
 A5|   CC1  |  SBU2  |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)
 A3| SSTXn1 | SSTXn2 |B10 (15)
 A2| SSTXp1 | SSTXp2 |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```
Common mistake with OpenAI's models: the USB3.1 pairs have mixed up TX/RX as well as numbers. Polarity is correct though! 3/4 points

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Below is the standard **USB Type‑C receptacle (female) pinout** as defined by the USB‑C spec. The receptacle has two “rows” of contacts, commonly labeled **A** and **B** (to support cable flip/orientation).

### USB‑C receptacle pinout (female)

| Pin | Signal | Function |
|---|---|---|
| A1 | GND | Ground |
| A2 | SSTXp1 | SuperSpeed TX (pair) |
| A3 | SSTXn1 | SuperSpeed TX (pair) |
| A4 | VBUS | +5 V (USB power; may be higher with USB‑PD) |
| A5 | CC1 | Configuration Channel (attach/orientation/PD) |
| A6 | D+ | USB 2.0 D+ |
| A7 | D− | USB 2.0 D− |
| A8 | SBU1 | Sideband use (Alt Modes, etc.) |
| A9 | VBUS | +5 V (USB power) |
| A10 | SSRXn2 | SuperSpeed RX (pair) |
| A11 | SSRXp2 | SuperSpeed RX (pair) |
| A12 | GND | Ground |
| B1 | GND | Ground |
| B2 | SSRXp1 | SuperSpeed RX (pair) |
| B3 | SSRXn1 | SuperSpeed RX (pair) |
| B4 | VBUS | +5 V (USB power) |
| B5 | CC2 | Configuration Channel (attach/orientation/PD) |
| B6 | D+ | USB 2.0 D+ |
| B7 | D− | USB 2.0 D− |
| B8 | SBU2 | Sideband use (Alt Modes, etc.) |
| B9 | VBUS | +5 V (USB power) |
| B10 | SSTXn2 | SuperSpeed TX (pair) |
| B11 | SSTXp2 | SuperSpeed TX (pair) |
| B12 | GND | Ground |

### Notes (common wiring details)
- **USB 2.0 lines are duplicated:** tie **A6 to B6 (D+)** and **A7 to B7 (D−)** on a receptacle.
- **CC pins:** use **CC1 and CC2** (don’t short them together). One will be active depending on plug orientation.
- **SuperSpeed pairs:** routing depends on whether you support USB 3.x and/or Alt Modes; orientation handling is typically done with a mux/switch.

If you tell me whether your connector is for a **device (UFP)** or **host (DFP)** and whether you need **USB2-only or USB3/PD**, I can also provide the typical schematic connections (Rp/Rd, VBUS switch, ESD, etc.).
```
