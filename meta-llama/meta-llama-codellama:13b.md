# meta-llama/codellama:13b

A large language model that can use text prompts to generate and discuss code.

## Results

- [ ] Number of pins (24)
- [ ] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12|    CC2 |        |B1  (24) 
A11|    CC1 |        |B2  (23)
A10|    TX2 |        |B3  (22)
 A9|    RX2 |        |B4  (21)
 A8|    TX1 | GND1   |B5  (20)
 A7|    RX1 | VBUS1  |B6  (19)
 A6|    GND | SBU4   |B7  (18)
 A5|   SBU2 | SBU3   |B8  (17)
 A4|   SBU1 | RX3    |B9  (16)
 A3|     D+ | TX3    |B10 (15)
 A2|     D- | GND    |B11 (14)
 A1|   Vbus | VBUS   |B12 (13)
```

Asking the same question over and over results in very different responses, similar to llama.

Barely comprehensible

Zero points.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

A female USB Type-C connector has the following pinout:

1. Vbus (5V power)
2. D- (data line)
3. D+ (data line)
4. SBU1 (bias voltage for the D+ and D- lines)
5. SBU2 (bias voltage for the D+ and D- lines)
6. GND (ground)
7. RX1 (receive data from the host to device)
8. TX1 (send data from the device to the host)
9. RX2 (receive data from the host to device)
10. TX2 (send data from the device to the host)
11. CC1 (communication channel 1, used for power delivery)
12. CC2 (communication channel 2, used for power delivery)
13. VBUS (power supply voltage, typically 5V)
14. GND (ground reference)
15. TX3 (optional transmit data line)
16. RX3 (optional receive data line)
17. SBU3 (bias voltage for the D+ and D- lines)
18. SBU4 (bias voltage for the D+ and D- lines)
19. VBUS1 (additional power supply voltage, typically 5V)
20. GND1 (additional ground reference)

Note: The pinout of a USB Type-C connector can vary depending on the specific implementation and application. The above pinout is for a standard USB Type-C connector that is commonly 
used in consumer electronics, but there may be variations in other applications.

```