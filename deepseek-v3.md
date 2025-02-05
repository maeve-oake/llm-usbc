# DeepSeek-V3

DeepSeek-V3 achieves a significant breakthrough in inference speed over previous models.
It tops the leaderboard among open-source models and rivals the most advanced closed-source models globally.

## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|    GND | GND    |B1  (24) 
A11|   RX2+ | RX2+   |B2  (23)
A10|   RX2- | RX2-   |B3  (22)
 A9|   VBus | VBus   |B4  (21)
 A8|   SBU1 | SBU1   |B5  (20)
 A7|     D- | D-     |B6  (19)
 A6|     D+ | D+     |B7  (18)
 A5|    CC1 | CC1    |B8  (17)
 A4|   VBus | VBus   |B9  (16)  # Example comment
 A3|   TX1- | TX1-   |B10 (15)
 A2|   TX1+ | TX1+   |B11 (14)
 A1|    GND | GND    |B12 (13)
```

DeepSeek had an interesting approach to listing the pins - the fancy diagram drawn has B1-12 not inversed, but the pin functions listed below are *almost* right! It unfortunately does not realise mirroring the pins directly isn't right for reversable connectors, therefore anything with polarity is flipper wrong. VBUS and GND is thankfully correct! 2 out of 4 points.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

The USB Type-C connector is a versatile and reversible connector that has become the standard for many modern devices. Below is the pinout for a female USB Type-C connector:

USB Type-C Female Connector Pinout (Top View):
 A1  A2  A3  A4  A5  A6  A7  A8  A9  A10 A11 A12
 ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┐
 │   │   │   │   │   │   │   │   │   │   │   │   │
 │   │   │   │   │   │   │   │   │   │   │   │   │
 └───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘
 B1  B2  B3  B4  B5  B6  B7  B8  B9  B10 B11 B12

Pin Functions:
A1 / B12: GND (Ground)

A2 / B11: TX1+ (SuperSpeed differential pair, Transmit)

A3 / B10: TX1- (SuperSpeed differential pair, Transmit)

A4 / B9: VBus (Power)

A5 / B8: CC1 (Configuration Channel)

A6 / B7: D+ (USB 2.0 differential pair)

A7 / B6: D- (USB 2.0 differential pair)

A8 / B5: SBU1 (Sideband Use)

A9 / B4: VBus (Power)

A10 / B3: RX2- (SuperSpeed differential pair, Receive)

A11 / B2: RX2+ (SuperSpeed differential pair, Receive)

A12 / B1: GND (Ground)

Key Points:
Reversibility: The USB Type-C connector is reversible, meaning the pinout is symmetrical. This allows the connector to be inserted in either orientation.

Configuration Channel (CC): The CC pins are used for cable orientation detection, USB PD (Power Delivery) communication, and other configuration tasks.

SuperSpeed Pairs: The TX and RX pairs are used for high-speed data transfer (USB 3.1/3.2).

USB 2.0 Pairs: The D+ and D- pins are used for USB 2.0 data transfer.

VBus: These pins provide power (typically 5V, but can be higher with USB PD).

SBU: Sideband Use pins are used for alternate modes like DisplayPort or Thunderbolt.

This pinout is essential for designing or troubleshooting USB Type-C connections, ensuring proper power delivery and data communication.
```