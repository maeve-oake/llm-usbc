# openai/gpt-5-mini

GPT-5 Mini is a compact version of GPT-5, designed to handle lighter-weight reasoning tasks.

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
A11| SSRX1- | SSTX2+ |B2  (23)
A10| SSRX1+ | SSTX2- |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|  SBU1  |  CC2   |B5  (20)
 A7|    D-  |  D+    |B6  (19)
 A6|    D+  |  D-    |B7  (18)
 A5|   CC1  |  SBU2  |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)
 A3| SSTX1- | SSRX2+ |B10 (15)
 A2| SSTX1+ | SSRX2- |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```

Everything's perfect, except RX2 and RX1 are swapped! Polarity is correct, i'd give 3.5 if possible. 3/4 points

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Below is the common pinout (signal assignment) for a USB Type‑C female receptacle (24 pins). The connector has two mirrored rows (A = top row, B = bottom row). Pin numbers run A1..A12 (top row left→right) and B1..B12 (bottom row left→right) as seen looking into the receptacle.

Summary (grouped by function)
- VBUS (power): A4, A9, B4, B9
- GND (ground): A1, A12, B1, B12
- USB 2.0 D+: A6, B6
- USB 2.0 D-: A7, B7
- Configuration Channel (CC): A5 (CC1), B5 (CC2)
- Sideband Use (SBU): A8 (SBU1), B8 (SBU2)
- SuperSpeed differential pairs (8 lanes total in two symmetric sets):
  - SSTX1+: A2
  - SSTX1-: A3
  - SSRX1+: A10
  - SSRX1-: A11
  - SSTX2+: B2
  - SSTX2-: B3
  - SSRX2+: B10
  - SSRX2-: B11

Putting it as a full pin list (A row then B row):
- A1: GND
- A2: SSTX1+
- A3: SSTX1-
- A4: VBUS
- A5: CC1
- A6: D+
- A7: D-
- A8: SBU1
- A9: VBUS
- A10: SSRX1+
- A11: SSRX1-
- A12: GND

- B1: GND
- B2: SSTX2+
- B3: SSTX2-
- B4: VBUS
- B5: CC2
- B6: D+
- B7: D-
- B8: SBU2
- B9: VBUS
- B10: SSRX2+
- B11: SSRX2-
- B12: GND

Notes and important points
- The connector is reversible: CC1/CC2 are used to detect plug orientation and select which SuperSpeed pairs are used for TX/RX in a given orientation.
- VCONN (when used to power active cables/adapters) is provided on the CC pin that is not used for orientation detection (i.e., whichever CC line is connected to the receptacle’s VCONN power path).
- The 4 VBUS pins and 4 GND pins are paralleled for current capacity.
- USB 2.0 D+/D- are duplicated on both A and B rows so USB2 works regardless of orientation.
- For exact mechanical footprint, pin numbering orientation, and USB‑IF compliant details (PD, Alternate Modes, cable types, shielding, impedance, etc.), consult the official USB‑IF Type‑C specification.

If you want a labeled diagram (image/ASCII) for a particular connector orientation or a mapping for a plug (male) instead of a receptacle, tell me which view you prefer and I’ll provide it.
```
