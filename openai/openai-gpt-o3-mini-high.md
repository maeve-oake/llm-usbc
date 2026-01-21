# openai/gpt-o3-mini-high

Model description.

## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [x] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|    GND | GND    |B1  (24) 
A11| SSRXn1 | SSTXp2 |B2  (23)
A10| SSRXp1 | SSTXn2 |B3  (22)
 A9|   VBUS | VBUS   |B4  (21)
 A8|   SBU1 | CC2    |B5  (20)
 A7|     D- | D+     |B6  (19)
 A6|     D+ | D-     |B7  (18)
 A5|    CC1 | SBU2   |B8  (17)
 A4|   VBUS | VBUS   |B9  (16)
 A3| SSTXn1 | SSRXp2 |B10 (15)
 A2| SSTXp1 | SSRXn2 |B11 (14)
 A1|    GND | GND    |B12 (13)
```

Unfortunately making the same mistake as o1 and o1-mini, o3-mini-high only slips up with backwards USB 3 superspeed polarity on pins A11, A10, B11 and B10. 3 out of 4 points.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Below is a summary of the standard 24‑pin layout for a USB Type‑C receptacle (female connector). The connector is symmetrical and reversible, meaning that depending on the orientation of the plug, one set of pins (either the A‑side or B‑side) will be connected. Each side has 12 pins:

A‑Side (Top Row):

A1: GND
A2: SSTXp1 (SuperSpeed transmit, positive)
A3: SSTXn1 (SuperSpeed transmit, negative)
A4: VBUS (Power)
A5: CC1 (Configuration Channel)
A6: D+ (USB 2.0 data)
A7: D– (USB 2.0 data)
A8: SBU1 (Sideband Use)
A9: VBUS (Power)
A10: SSRXp1 (SuperSpeed receive, positive)
A11: SSRXn1 (SuperSpeed receive, negative)
A12: GND
B‑Side (Bottom Row):

B1: GND
B2: SSTXp2 (SuperSpeed transmit, positive)
B3: SSTXn2 (SuperSpeed transmit, negative)
B4: VBUS (Power)
B5: CC2 (Configuration Channel)
B6: D+ (USB 2.0 data)
B7: D– (USB 2.0 data)
B8: SBU2 (Sideband Use)
B9: VBUS (Power)
B10: SSRXp2 (SuperSpeed receive, positive)
B11: SSRXn2 (SuperSpeed receive, negative)
B12: GND
Additional Notes:

Reversible Design: Only one of the two sets (A‑side or B‑side) is active in any given connection, determined by the plug’s orientation.
USB 2.0 Lines: The D+ and D– pins appear on both sides but are typically tied together internally to support USB 2.0 signaling.
Alternate Modes: The SBU pins may be used for alternate modes (such as audio or DisplayPort), depending on the design.
This pinout conforms to the USB Type‑C specification as defined by the USB Implementers Forum (USB‑IF).
```