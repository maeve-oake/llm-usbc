# meta-llama/llama-4-maverick

Llama 4 Maverick 17B Instruct (128E) is a high-capacity multimodal language model from Meta, built on a mixture-of-experts (MoE) architecture with 128 experts and 17 billion active parameters per forward pass (400B total).

## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|   GND  |  GND   |B1  (24) 
A11| SSTXp2 | SSTXp2 |B2  (23)
A10| SSTXn2 | SSTXn2 |B3  (22)
 A9|  VBUS  |  VBUS  |B4  (21)
 A8|   SBU  | VCONN  |B5  (20)
 A7|    Dn  |  Dn    |B6  (19)
 A6|    Dp  |  Dp    |B7  (18)
 A5|    CC  |  SBU   |B8  (17)
 A4|  VBUS  |  VBUS  |B9  (16)
 A3| SSTXn1 | SSTXn1 |B10 (15)
 A2| SSTXp1 | SSTXp1 |B11 (14)
 A1|   GND  |  GND   |B12 (13)
```

Unfortunately llama-4 maverick got one side of the USB 2 polarity backwards, as well as various other mistakes with CC and USB3.1 scoring it 2/4 points.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

The USB Type-C connector is a versatile and reversible connector that can be used for both data transfer and power delivery. Here is the pinout for a female USB Type-C connector:

**Pinout:**

The USB Type-C connector has 24 pins, arranged in a 2x12 grid. The pins are labeled A1-A12 and B1-B12. The pinout is as follows:

**A-Side:**

1. A1: GND (Ground)
2. A2: SSTXp1 (SuperSpeed transmit pair 1, positive)
3. A3: SSTXn1 (SuperSpeed transmit pair 1, negative)
4. A4: VBUS (Power)
5. A5: CC (Configuration Channel)
6. A6: Dp (USB 2.0 differential pair, positive)
7. A7: Dn (USB 2.0 differential pair, negative)
8. A8: SBU (Sideband Use)
9. A9: VBUS (Power)
10. A10: SSTXn2 (SuperSpeed transmit pair 2, negative)
11. A11: SSTXp2 (SuperSpeed transmit pair 2, positive)
12. A12: GND (Ground)

**B-Side:**

1. B1: GND (Ground)
2. B2: SSTXp2 (SuperSpeed transmit pair 2, positive)
3. B3: SSTXn2 (SuperSpeed transmit pair 2, negative)
4. B4: VBUS (Power)
5. B5: VCONN (Power for active cables)
6. B6: Dn (USB 2.0 differential pair, negative)
7. B7: Dp (USB 2.0 differential pair, positive)
8. B8: SBU (Sideband Use)
9. B9: VBUS (Power)
10. B10: SSTXn1 (SuperSpeed transmit pair 1, negative)
11. B11: SSTXp1 (SuperSpeed transmit pair 1, positive)
12. B12: GND (Ground)

**Key Features:**

* The USB Type-C connector has a reversible design, meaning that it can be inserted either way.
* The CC (Configuration Channel) pin is used to detect the orientation of the connector and configure the connection.
* The SBU (Sideband Use) pin is used for alternate mode (Alt Mode) signaling.
* The VCONN pin is used to power active cables.
* The SSTX and SSTXn pins are used for SuperSpeed data transfer.
* The Dp and Dn pins are used for USB 2.0 data transfer.

**Notes:**

* The USB Type-C connector is designed to be used with a variety of protocols, including USB, DisplayPort, and Power Delivery.
* The pinout may vary depending on the specific application and configuration.

I hope this helps! Let me know if you have any further questions.
```
