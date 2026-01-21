# openai/gpt-5

GPT-5 is OpenAI’s most advanced model, offering major improvements in reasoning, code quality, and user experience.

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
A11|  RX1-  |  RX2-  |B2  (23)
A10|  RX1+  |  RX2+  |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|  SBU1  |  CC2   |B5  (20)
 A7|    D-  |  D+    |B6  (19)
 A6|    D+  |  D-    |B7  (18)
 A5|   CC1  |  SBU2  |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)
 A3|  TX1-  |  TX2-  |B10 (15)
 A2|  TX1+  |  TX2+  |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```

GPT only made a mistake with the USB3.1 SS lines, getting polarity, RX/TX and numbering mixed up. 3/4 points

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Here is the standard pinout for a USB Type‑C receptacle (female). Viewpoint: looking into the front of the receptacle.

A-side (A1–A12):
- A1: GND
- A2: TX1+
- A3: TX1-
- A4: VBUS
- A5: CC1
- A6: D+
- A7: D-
- A8: SBU1
- A9: VBUS
- A10: RX1+
- A11: RX1-
- A12: GND

B-side (B1–B12):
- B1: GND
- B2: RX2-
- B3: RX2+
- B4: VBUS
- B5: CC2
- B6: D+
- B7: D-
- B8: SBU2
- B9: VBUS
- B10: TX2-
- B11: TX2+
- B12: GND

Notes:
- Shield/shell: chassis ground.
- VBUS appears on four pins (A4, A9, B4, B9); GND on four pins (A1, A12, B1, B12).
- USB 2.0 data: D+ (A6, B6) and D- (A7, B7).
- Configuration/channel: CC1 (A5), CC2 (B5).
- Sideband use: SBU1 (A8), SBU2 (B8).
- SuperSpeed differential pairs: TX1 (A2/A3), RX1 (A10/A11), TX2 (B11/B10), RX2 (B3/B2).
```
