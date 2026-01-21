# google/gemini-2.5-pro

Gemini 2.5 Pro is Google’s state-of-the-art AI model designed for advanced reasoning, coding, mathematics, and scientific tasks. 

## Results

- [X] Number of pins (24)
- [X] VBUS and GND pins
- [X] USB 2.0 pins
- [ ] All other pins

Gemini got the B side of the connector backwards, (A1 should be opposite B12). Despite this, USB2 data lines are the correct polarity, and sideband CC lines are also correct. USB3.1 has the correct polarity but swapped TX / RX lines.

Interestingly, Gemini 2.0 did not have the same issues with the B side of the connector, but did have the same USB3.1 TX / RX mess.

3/4 points!

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|   GND  |  GND   |B1  (24) 
A11|  RX2+  |  RX1+  |B2  (23)
A10|  RX2-  |  RX1-  |B3  (22)
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
Comments and notes go here.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Of course. Here is the detailed pinout for a standard **female USB Type-C connector** (also known as a receptacle), which is the port you would find on a device like a laptop, phone, or charger.

### Visual Representation

A female USB-C receptacle has 24 pins, arranged in two rows of 12 (Top Row A and Bottom Row B). The pins are mirrored so that the connector is reversible.


       <-- Front of Receptacle -->

         A12  A11  A10  A9   A8   A7   A6   A5   A4   A3   A2   A1
        +---------------------------------------------------------+
        |  o    o    o    o    o    o    o    o    o    o    o    o  |  <- Top Row (A)
        |                                                         |
        |  o    o    o    o    o    o    o    o    o    o    o    o  |  <- Bottom Row (B)
        +---------------------------------------------------------+
         B12  B11  B10  B9   B8   B7   B6   B5   B4   B3   B2   B1



---

### Pinout Table

Here is the function of each pin. Notice the symmetry between Row A and Row B, which is the key to the connector's reversibility.

| Pin | Name | Description | Pin | Name | Description |
| :-- | :--- | :---------------------------------- | :-- | :--- | :---------------------------------- |
| **A1**| GND | Ground Return | **B1**| GND | Ground Return |
| **A2**| TX1+ | SuperSpeed Differential Pair #1, Transmit (+) | **B2**| RX1+ | SuperSpeed Differential Pair #1, Receive (+) |
| **A3**| TX1- | SuperSpeed Differential Pair #1, Transmit (-) | **B3**| RX1- | SuperSpeed Differential Pair #1, Receive (-) |
| **A4**| V<sub>BUS</sub> | Bus Power (for charging and devices) | **B4**| V<sub>BUS</sub> | Bus Power |
| **A5**| CC1 | **Configuration Channel** | **B5**| CC2 | **Configuration Channel** |
| **A6**| D+ | USB 2.0 Differential Pair, Data (+) | **B6**| D+ | USB 2.0 Differential Pair, Data (+) |
| **A7**| D- | USB 2.0 Differential Pair, Data (-) | **B7**| D- | USB 2.0 Differential Pair, Data (-) |
| **A8**| SBU1 | Sideband Use (for Alternate Modes) | **B8**| SBU2 | Sideband Use (for Alternate Modes) |
| **A9**| V<sub>BUS</sub> | Bus Power | **B9**| V<sub>BUS</sub> | Bus Power |
| **A10**| RX2- | SuperSpeed Differential Pair #2, Receive (-) | **B10**| TX2- | SuperSpeed Differential Pair #2, Transmit (-) |
| **A11**| RX2+ | SuperSpeed Differential Pair #2, Receive (+) | **B11**| TX2+ | SuperSpeed Differential Pair #2, Transmit (+) |
| **A12**| GND | Ground Return | **B12**| GND | Ground Return |

---

### Functional Pin Groups Explained

To make it easier to understand, the 24 pins can be grouped by their function.

#### 1. Power Pins (V<sub>BUS</sub> and GND)
*   **Pins:** A4, A9, B4, B9 (V<sub>BUS</sub>) and A1, A12, B1, B12 (GND).
*   **Function:** These are the power and ground lines. Having multiple pins for both V<sub>BUS</sub> and Ground allows the connector to handle much higher currents (up to 5A) than previous USB types, which is essential for **USB Power Delivery (USB-PD)** to charge devices like laptops.

#### 2. USB 2.0 Pins (D+ and D-)
*   **Pins:** A6, A7, B6, B7.
*   **Function:** This is the standard data pair for backward compatibility with USB 2.0. Although there are two pairs (one on each row), only one pair is ever active at a time, depending on the cable's orientation.

#### 3. High-Speed Data Pins (TX/RX Pairs)
*   **Pins:** TX1+/-, TX2+/- and RX1+/-, RX2+/-.
*   **Function:** These are four differential pairs used for high-speed data transfer (USB 3.x, USB4, Thunderbolt, DisplayPort).
    *   In a standard USB 3.x connection, only two of these pairs are used (one for transmitting, one for receiving).
    *   For higher speeds like USB4 or some Alternate Modes, all four pairs can be used simultaneously.
    *   The reversible design means that `TX1` on Row A lines up with `RX1` on Row B, and vice-versa, allowing the host to route the signals correctly no matter how the cable is plugged in.

#### 4. Configuration Channel Pins (CC1 and CC2)
*   **Pins:** A5 (CC1) and B5 (CC2).
*   **This is the "brain" of the USB-C connector.** It handles several critical functions:
    *   **Orientation Detection:** The USB-C plug only has one CC pin. The receptacle has two (CC1, CC2). The device detects which of the two receptacle pins is connected to determine if the cable is flipped or not.
    *   **Power Negotiation:** The CC line is used for the **USB Power Delivery (USB-PD)** communication protocol, where the device and charger "talk" to negotiate the voltage and current (e.g., 20V at 5A).
    *   **Alternate Mode (Alt Mode) Entry:** The CC line is used to signal that the high-speed data pins should be switched from USB mode to another protocol, like **DisplayPort** or **Thunderbolt**.
    *   **V<sub>CONN</sub> Supply:** The CC pin that is *not* used for communication can be repurposed to provide power (V<sub>CONN</sub>) to chips inside electronically-marked cables (e.g., active Thunderbolt cables or cables rated for 5A).

#### 5. Sideband Use Pins (SBU1 and SBU2)
*   **Pins:** A8 (SBU1) and B8 (SBU2).
*   **Function:** These are auxiliary pins used for additional signals required by certain Alternate Modes. The most common use is for the AUX channel in **DisplayPort Alt Mode**, which handles secondary data like monitor configuration.
```
