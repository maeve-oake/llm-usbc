# google/gemma4:26B

Gemma 4 models are designed to deliver frontier-level performance at each size. They are well-suited for reasoning, agentic workflows, coding, and multimodal understanding.

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
A11|  RX2-  |  TX2+  |B2  (23)
A10|  RX2+  |  TX2-  |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|  SBU2  |  CC2   |B5  (20)
 A7|   D-   |   D+   |B6  (19)
 A6|   D+   |   D-   |B7  (18)
 A5|   CC1  |  SBU1  |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)  # Example comment
 A3|  TX1-  |  RX1+  |B10 (15)
 A2|  TX1+  |  RX1-  |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```
3/4, almost perfect. RX1 and RX2 have the wrong polarity.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector
Thinking...

*   Subject: Female USB Type-C connector.
*   Goal: Provide the pinout.
*   Constraint: Needs to be accurate, clear, and organized.

    *   USB-C is complex because it's reversible and has multiple modes (USB 2.0, USB 3.1/3.2/4, Thunderbolt, Power 
Delivery).
    *   The connector has 24 pins total (12 on each side).
    *   The pins are arranged in two rows: A (top) and B (bottom).

    *   *A-side (Top):* A1, A2, A3, A4, A5, A6, A7, A8, A9, A10, A11, A12.
    *   *B-side (Bottom):* B1, B2, B3, B4, B5, B6, B7, B8, B9, B10, B11, B12.

    *   *Group 1: Power/Ground*
        *   GND: A1, A12, B1, B12.
        *   VBUS: A4, A9, B4, B9.

    *   *Group 2: Configuration/Detection (Crucial for USB-C)*
        *   CC1, CC2 (Configuration Channel): A5, B5. (Note: Only one is used per cable connection).
        *   SBU1, SBU2 (Sideband Use): A8, B8.

    *   *Group 3: USB 2.0 (D+/D-)*
        *   D+: A6, B6.
        *   D-: A7, B7.

    *   *Group 4: High-Speed Differential Pairs (USB 3.x/Thunderbolt)*
        *   TX1+/-, TX1+/- (Transmit)
        *   RX1+/-, RX1+/- (Receive)
        *   TX2+/-, TX2+/-
        *   RX2+/-, RX2+/-
        *   (A2, A3, A10, A11; B2, B3, B10, B11)

    *   *Introduction:* Mention there are 24 pins.
    *   *Table/List Format:* A table is best for side-by-side comparison of A and B rows.
    *   *Categorization:* Group pins by function (Power, Data, Config, etc.) to help the user understand *why* they 
exist.
    *   *Important Notes:* Add warnings/nuances (CC pins, Reversibility, High Speed).

    *   *Wait, let's check the pin mapping carefully.*
        *   A1/B1: GND
        *   A2/B2: TX1+ (High Speed)
        *   A3/B3: TX1- (High Speed)
        *   A4/B4: VBUS
        *   A5/B5: CC1/CC2
        *   A6/B6: D+ (USB 2.0)
        *   A7/B7: D- (USB 2.0)
        *   A8/B8: SBU2/SBU1
        *   A9/B9: VBUS
        *   A10/B10: RX1- (High Speed)
        *   A11/B11: RX1+ (High Speed)
        *   A12/B12: GND

    *   *Correction on A10/A11:* Usually, the mapping is:
        A2, A3 (TX1)
        A10, A11 (RX1)
        B2, B3 (TX2)
        B10, B11 (RX2)
        *Wait, let's look at the standard pinout layout for A and B rows.*

    *   *Standard Pinout (Official):*
        A1/B1: GND
        A2/B2: TX1+
        A3/B3: TX1-
        A4/B4: VBUS
        A5/B5: CC1/CC2
        A6/B6: D+
        A7/B7: D-
        A8/B8: SBU2/SBU1
        A9/B9: VBUS
        A10/B10: RX2+
        A11/B11: RX2-
        A12/B12: GND

    *Actually, for the High-Speed pairs:*
    Row A: A2/A3 (TX1), A10/A11 (RX2)
    Row B: B2/B3 (TX2), B10/B11 (RX1)
    *This allows the signal to be routed correctly regardless of orientation.*

    *   Organize into a clear table.
    *   Add a functional summary.
    *   Add technical warnings (CC pins are vital!).
...done thinking.

A USB Type-C connector is much more complex than previous USB standards because it is **reversible** and supports 
multiple protocols (USB 2.0, USB 3.2/4, Thunderbolt, and Power Delivery).

A full-featured female USB-C receptacle has **24 pins** (12 on the top row, labeled **A**, and 12 on the bottom row, 
labeled **B**).

### USB Type-C Pinout Table

| Pin | Side A (Top) | Side B (Bottom) | Function |
| :--- | :--- | :--- | :--- |
| **1** | **GND** | **GND** | Ground |
| **2** | **TX1+** | **TX2+** | High-Speed Transmit (+) |
| **3** | **TX1-** | **TX2-** | High-Speed Transmit (-) |
| **4** | **VBUS** | **VBUS** | Power (5V, 9V, 15V, 20V, etc.) |
| **5** | **CC1** | **CC2** | Configuration Channel (Detection/Negotiation) |
| **6** | **D+** | **D+** | USB 2.0 Data (+) |
| **7** | **D-** | **D-** | USB 2.0 Data (-) |
| **8** | **SBU2** | **SBU1** | Sideband Use (Alternate Modes) |
| **9** | **VBUS** | **VBUS** | Power (5V, 9V, 15V, 20V, etc.) |
| **10** | **RX2+** | **RX1+** | High-Speed Receive (+) |
| **11** | **RX2-** | **RX1-** | High-Speed Receive (-) |
| **12** | **GND** | **GND** | Ground |

---

### Functional Groupings

To understand how the connector works, it is easier to look at the pins in groups:

#### 1. Power and Ground (The "Heavy Lifters")
*   **GND (A1, B1, A12, B12):** Provides the return path for current.
*   **VBUS (A4, B4, A9, B9):** The main power lines. Because USB-C supports high wattage (up to 240W in EPR), these pins 
are duplicated to handle higher current safely.

#### 2. Configuration and Communication (The "Brains")
*   **CC1 / CC2 (A5, B5):** These are the most important pins for USB-C logic. When you plug a cable in, the device uses 
the CC pins to detect orientation (which way the plug is facing) and to negotiate **Power Delivery (PD)** (e.g., "I need 
20V/3A").
*   **SBU1 / SBU2 (A8, B8):** "Sideband Use." These pins are used for non-USB functions, such as audio signals in "Audio 
Adapter Accessory Mode" or auxiliary data in DisplayPort Alt Mode.

#### 3. USB 2.0 Data (The "Legacy")
*   **D+ / D- (A6, B6, A7, B7):** These are the standard differential pairs used for USB 2.0 communication. Even in 
high-speed USB 4 cables, these pins are present for backward compatibility.

#### 4. High-Speed Data (The "Speedsters")
*   **TX / RX Pairs (A2, A3, A10, A11 and B2, B3, B10, B11):** These eight pins form four differential pairs used for 
SuperSpeed USB (3.0, 3.1, 3.2, 4) and Thunderbolt. They allow for massive data throughput by sending and receiving data 
simultaneously at very high frequencies.

---

### Important Engineering Notes:

1.  **Orientation Logic:** Because the connector is reversible, the CC pin is used to determine if the cable is 
"flipped." If the device detects a signal on CC1, it knows the orientation and routes the high-speed data lines (TX/RX) 
accordingly.
2.  **The "CC" Requirement:** If you are designing a DIY charger or device, **you cannot simply connect VBUS to power.** 
You must have a CC controller (or a pull-down resistor of 5.1kΩ on the CC pins) to tell the source (like a laptop or 
wall brick) to actually turn on the power.
3.  **Shorting Warning:** High-speed pins (TX/RX) are extremely sensitive to impedance. If you are designing a PCB, 
these must be routed as differential pairs with controlled impedance, or the high-speed data will fail.

```