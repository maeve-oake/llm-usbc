# x-ai/grok-4

Grok 4 is xAI's latest reasoning model with a 256k context window.

## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [x] USB 2.0 pins
- [x] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|   GND  |  GND   |B1  (24) 
A11|  RX2+  |  TX2+  |B2  (23)
A10|  RX2-  |  TX2-  |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|  SBU1  |  CC2   |B5  (20)
 A7|    D-  |  D+    |B6  (19)
 A6|    D+  |  D-    |B7  (18)
 A5|   CC1  |  SBU2  |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)  # Example comment
 A3|  TX1-  |  RX1-  |B10 (15)
 A2|  TX1+  |  RX1+  |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```
Perfect score, 4/4!

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Below is a detailed pinout for a standard female USB Type-C connector (also known as the receptacle, typically found on devices like laptops, phones, or hubs). USB Type-C uses a 24-pin reversible design, with pins arranged in two rows (A and B) for symmetry. The pin numbering starts from one end and goes to the other, with A1-A12 on the top row and B1-B12 on the bottom row when viewed with the connector opening facing you and the tongue in the middle.

### Visual Representation
Imagine the connector as a rectangular slot with pins on both sides of the central tongue:


   A1                A12
   ┌──────────────────┐
   │                  │
   │  (Tongue here)   │
   │                  │
   └──────────────────┘
   B12               B1


### Pin Assignments
Here's the standard pinout based on the USB Implementers Forum (USB-IF) specifications. Note that some pins are duplicated for reversibility (e.g., data lines for USB 2.0). The functions can vary slightly depending on the mode (e.g., USB 2.0, USB 3.x, Power Delivery, DisplayPort Alt Mode), but this is the core mapping:

#### Top Row (A1 to A12)
- **A1**: GND (Ground)
- **A2**: TX1+ (SuperSpeed transmit positive, for USB 3.x data lane 1)
- **A3**: TX1- (SuperSpeed transmit negative, for USB 3.x data lane 1)
- **A4**: VBUS (Bus power, +5V nominal, up to 20V with Power Delivery)
- **A5**: CC1 (Configuration Channel 1, for orientation detection, power role, and alternate modes)
- **A6**: D+ (USB 2.0 data positive)
- **A7**: D- (USB 2.0 data negative)
- **A8**: SBU1 (Sideband Use 1, for alternate modes like DisplayPort or audio)
- **A9**: VBUS (Bus power, +5V nominal, up to 20V with Power Delivery)
- **A10**: RX2- (SuperSpeed receive negative, for USB 3.x data lane 2)
- **A11**: RX2+ (SuperSpeed receive positive, for USB 3.x data lane 2)
- **A12**: GND (Ground)

#### Bottom Row (B1 to B12)
- **B1**: GND (Ground)
- **B2**: TX2+ (SuperSpeed transmit positive, for USB 3.x data lane 2)
- **B3**: TX2- (SuperSpeed transmit negative, for USB 3.x data lane 2)
- **B4**: VBUS (Bus power, +5V nominal, up to 20V with Power Delivery)
- **B5**: CC2 (Configuration Channel 2, for orientation detection, power role, and alternate modes)
- **B6**: D+ (USB 2.0 data positive)
- **B7**: D- (USB 2.0 data negative)
- **B8**: SBU2 (Sideband Use 2, for alternate modes like DisplayPort or audio)
- **B9**: VBUS (Bus power, +5V nominal, up to 20V with Power Delivery)
- **B10**: RX1- (SuperSpeed receive negative, for USB 3.x data lane 1)
- **B11**: RX1+ (SuperSpeed receive positive, for USB 3.x data lane 1)
- **B12**: GND (Ground)

### Key Notes
- **Reversibility**: The connector is designed to work in either orientation. When plugged in, the device detects the orientation via the CC pins (CC1 or CC2) and routes signals accordingly.
- **Power**: VBUS pins can deliver up to 100W (20V/5A) with USB Power Delivery (PD). GND pins provide the return path.
- **Data Lanes**: USB 3.x uses differential pairs (TX/RX) for high-speed data (up to 20 Gbps in USB4). USB 2.0 falls back to the D+/D- pins.
- **Alternate Modes**: Pins like SBU and CC enable features such as video output (e.g., HDMI or DisplayPort over USB-C) or Thunderbolt.
- **Variations**: This is for a full-featured USB Type-C receptacle. Some implementations (e.g., in cheap cables or devices) may omit SuperSpeed pins for cost savings, supporting only USB 2.0.
- **Safety Tip**: If you're working with hardware, ensure proper ESD protection and verify compatibility to avoid damage. For custom projects, refer to the official USB-IF specifications or datasheets from manufacturers like Molex or Hirose.

If you need more details (e.g., for a male plug, wiring diagrams, or specific use cases like USB PD), let me know!
```
