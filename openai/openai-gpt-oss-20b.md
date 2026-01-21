# Model name gpt‑oss‑20b

Open‑source, 20B‑parameter model from OpenAI running localy, with reasoning effort:High.

## Results

- [X] Number of pins (24)
- [ ] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12| VBUS   | VBUS   |B1  (24) 
A11| GND    | GND    |B2  (23)
A10| RX+1   | CC2    |B3  (22)
 A9| RX-1   | D-     |B4  (21)
 A8| TX+1   | D+     |B5  (20)
 A7| TX-1   | SBU2   |B6  (19)
 A6| SBU1   | TX-2   |B7  (18)
 A5| D+     | TX+2   |B8  (17)
 A4| D-     | RX-2   |B9  (16)  
 A3| CC1    | RX+2   |B10 (15)
 A2| VBUS   | GND    |B11 (14)
 A1| GND    | VBUS   |B12 (13)
```

It took 63 seconds to generate this answer on RX 7900 XT.


## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

**USB‑Type‑C (female) pin‑out**

The USB‑C connector has **24 contacts arranged in two symmetrical rows of 12 pins**.  
When looking at the plug with the USB logo facing up, the left‑hand side is the **A‑row** and the right‑hand side is the **B‑row**.

| Row | Pin # (in row) | Function | Notes |
|-----|----------------|----------|-------|
| **A‑row (top)** | A1 | GND | Ground |
|  | A2 | VBUS | 5 V supply (up to 3 A, PD‑controlled) |
|  | A3 | CC1 | Configurable “CC” pin – used for cable orientation and Power‑Delivery negotiation |
|  | A4 | D‑ | USB‑2.0 data line (full‑speed/low‑speed) |
|  | A5 | D+ | USB‑2.0 data line |
|  | A6 | SBU1 | Sideband pin – used for alternate modes (e.g., DisplayPort, Thunderbolt) |
|  | A7 | TX‑1 | SuperSpeed transmit lane 1 (differential pair TX‑/TX+) |
|  | A8 | TX+1 | SuperSpeed transmit lane 1 |
|  | A9 | RX‑1 | SuperSpeed receive lane 1 (RX‑/RX+) |
|  | A10 | RX+1 | SuperSpeed receive lane 1 |
|  | A11 | GND | Ground |
|  | A12 | VBUS | 5 V supply (same as A2) |

| **B‑row (bottom)** | B1 | VBUS | 5 V supply (mirror of A2) |
|  | B2 | GND | Ground (mirror of A11) |
|  | B3 | CC2 | Configurable “CC” pin – used for cable orientation and PD negotiation |
|  | B4 | D‑ | USB‑2.0 data line (mirror of A4) |
|  | B5 | D+ | USB‑2.0 data line (mirror of A5) |
|  | B6 | SBU2 | Sideband pin – mirror of A6 |
|  | B7 | TX‑2 | SuperSpeed transmit lane 2 (TX‑/TX+) |
|  | B8 | TX+2 | SuperSpeed transmit lane 2 |
|  | B9 | RX‑2 | SuperSpeed receive lane 2 (RX‑/RX+) |
|  | B10 | RX+2 | SuperSpeed receive lane 2 |
|  | B11 | GND | Ground (mirror of A1) |
|  | B12 | VBUS | 5 V supply (mirror of A12) |

---

### 24‑pin numeric numbering (often used in datasheets)

If you count the pins from left to right on the top row and then continue counting on the bottom row, the mapping is:

| Pin # | Contact | Function |
|-------|---------|----------|
| 1 | A1 | GND |
| 2 | A2 | VBUS |
| 3 | A3 | CC1 |
| 4 | A4 | D‑ |
| 5 | A5 | D+ |
| 6 | A6 | SBU1 |
| 7 | A7 | TX‑1 |
| 8 | A8 | TX+1 |
| 9 | A9 | RX‑1 |
|10 | A10 | RX+1 |
|11 | A11 | GND |
|12 | A12 | VBUS |
|13 | B1 | VBUS |
|14 | B2 | GND |
|15 | B3 | CC2 |
|16 | B4 | D‑ |
|17 | B5 | D+ |
|18 | B6 | SBU2 |
|19 | B7 | TX‑2 |
|20 | B8 | TX+2 |
|21 | B9 | RX‑2 |
|22 | B10 | RX+2 |
|23 | B11 | GND |
|24 | B12 | VBUS |

---

### Quick reference

| Signal | Purpose | Typical usage in a cable |
|--------|---------|--------------------------|
| **VBUS** | 5 V power (up to 3 A, PD‑controlled) | Always present on the connector; used for charging and data. |
| **GND** | Common ground | Always present. |
| **CC1 / CC2** | Cable orientation detection & Power Delivery negotiation | Must be present in all USB‑C cables; they connect to pull‑up/pull‑down resistors on host or device side. |
| **D‑ / D+** | USB‑2.0 data (full/low speed) | Used when the cable is a “USB‑A → C” or “USB‑B → C” cable that supports legacy USB‑2.0. |
| **TX/RX lanes** | SuperSpeed (USB 3.x) data | Present in cables that support 5 Gb/s, 10 Gb/s, or 20 Gb/s. |
| **SBU1 / SBU2** | Alternate mode sideband (DisplayPort, Thunderbolt, etc.) | Usually unused unless the cable is an alternate‑mode cable. |

---

### Orientation notes

* The connector is **symmetrical**, so a plug can be inserted in either orientation.  
* The CC pins determine the orientation: the host/device will detect which of the two CC pins (CC1 or CC2) is connected to its pull‑up resistor and then adjust the data/Power Delivery path accordingly.  
* Because of this symmetry, any USB‑C plug can be used with a female port regardless of how it’s inserted – the CC pins will automatically indicate the correct direction.

---

### References

* **USB‑IF Type‑C Connector Specification** (v1.3 and later) – official pinout diagram.  
* Texas Instruments “USB‑C Connector Pinout” datasheet (e.g., TUSB1106, TUSB1105).  
* *USB 2.0, USB 3.x, and USB‑C pin assignments* – various vendor application notes.

Feel free to ask if you need more detail on any particular signal or alternate mode usage!
```
