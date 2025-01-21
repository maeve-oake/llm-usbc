# Phi-4 14b

Phi-4 is a 14B parameter, state-of-the-art open model from Microsoft.

## Results

WIP.

## LLM Pinout

```
 A1|    D+   SBU1+  |B12 (13)
 A2|    D-   SBU1-  |B11 (14)
 A3|   CC1   GND    |B10 (15)
 A4|  VBUS          |B9  (16) # 16th Pin not specified
 A5| SSTX+   SSTX2+ |B8  (17)
 A6| SSTX-   SSTX2- |B7  (18)
 A7|   CC2   SSRX2+ |B6  (19)
 A8| SSRX+   SSRX2- |B5  (20)
 A9|  VBUS   VBUS   |B4  (21)
A10| SSRX-   GND    |B3  (22)
A11|   GND   GND    |B2  (23)
A12|   GND   SBU2+  |B1  (24)
             SBU2-  |B?? (25) # Hallucinated 25th Pin
```

## Raw LLM Output:

>>> Provide the pinout of a female USB Type-C connector

A female USB Type-C connector has 24 pins, arranged in two rows with 12 pins each. Here 
is a general outline of the pinout:

### Power and Ground Pins:
- **Pin 4 (VBUS):** VBUS +5V supply from the upstream source.
- **Pin 9 (VBUS):** VBUS +5V supply for high power delivery or charging.
- **Pin 12 (GND):** Ground.
- **Pin 15 (GND):** Ground.
- **Pin 20 (GND):** Ground.
- **Pin 23 (GND):** Ground.

### Data Pins:
- **Pins 1, 2, 3 (TX/ RX pairs for USB 2.0):**
  - Pin 1: D+ (USB 2.0)
  - Pin 2: D- (USB 2.0)
  - Pin 3: CC1 (Configuration Channel 1)

- **Pins 5, 6, 7 (TX/ RX pairs for USB 3.0):**
  - Pin 5: SSTX+
  - Pin 6: SSTX-
  - Pin 7: CC2 (Configuration Channel 2)
  
- **Pins 8, 10, 11 (RX/ TX pairs for USB 3.0):**
  - Pin 8: SSRX+ 
  - Pin 10: SSRX-
  - Pin 11: GND

- **Pins 13, 14, 17, 18, 19, 21, 22 (USB 3.1 SuperSpeed pairs):**
  - Pins 13 and 24: SBU1+/SBU2+ (Sideband Use)
  - Pins 14 and 25: SBU1-/SBU2- (Sideband Use)
  - Pin 17: SSTX2+
  - Pin 18: SSTX2-
  - Pin 19: SSRX2+
  - Pin 21: SSRX2-
  - Pin 22: GND

### Additional Pins:
- **Pin 4 and 9 (VBUS):** Provide power to connected devices.
- **Pins 3 and 7 (CC1/CC2):** Configuration Channel, used for cable orientation 
detection, current advertising, and alternate mode signaling.

This configuration allows USB Type-C connectors to support multiple roles (host, device), 
alternate modes like DisplayPort or HDMI, and higher power delivery compared to previous 
USB standards. The actual use of these pins can vary depending on the specific 
implementation and requirements of the connected devices and cables.


