# google/gemini-2.0-pro



## Results

- [x] Number of pins (24)
- [x] VBUS and GND pins
- [x] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
A12| GND    | GND    |B1  (24) # Ground return.
A11| RX2+   | RX2+   |B2  (23) # Receiver differential pair 2, positive. Used for SuperSpeed USB data transmission (one direction).
A10| RX2-   | RX2-   |B3  (22) # Receiver differential pair 2, negative. Used for SuperSpeed USB data transmission (one direction).
 A9| VBUS   | VBUS   |B4  (21) # Power bus. Carries the main power supply voltage.
 A8| SBU1   | SBU1   |B5  (20) # Sideband Use 1. Used for alternate modes (e.g., DisplayPort AUX channel). Its specific function depends on the negotiated alternate mode.
 A7| D-     | D-     |B6  (19) # USB 2.0 differential pair, negative. Used for USB 2.0 data transmission (half-duplex). Also used for some configuration signaling during connection.
 A6| D+     | D+     |B7  (18) # USB 2.0 differential pair, positive. Used for USB 2.0 data transmission (half-duplex). Also used for some configuration signaling during connection.
 A5| CC1    | CC1    |B8  (17) # Configuration Channel 1. Used for connection detection, cable orientation detection, power delivery negotiation, and alternate mode configuration. One of these two pins (CC1 or CC2) will be pulled low by the cable to indicate orientation.
 A4| VBUS   | VBUS   |B9  (16) # Power bus. Carries the main power supply voltage.
 A3| TX1-   | TX1-   |B10 (15) # Transmitter differential pair 1, negative. Used for SuperSpeed USB data transmission (one direction).
 A2| TX1+   | TX1+   |B11 (14) # Transmitter differential pair 1, positive. Used for SuperSpeed USB data transmission (one direction).
 A1| GND    | GND    |B12 (13) # Ground return. Essential for power and signal integrity.
```

Although Gemini 2.0 pro got the connector orientation correct, it seems to have not flipped USB3.1 polarity correctly. 3/4 points

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Okay, here's a breakdown of the USB Type-C female connector (receptacle) pinout, along with explanations and important considerations:

Understanding the Complexity

USB Type-C is significantly more complex than older USB connectors due to its reversibility, multiple power delivery modes, and support for alternate modes (like DisplayPort, Thunderbolt, etc.). It's crucial to understand that not all pins are used in all applications. The specific pins used depend on the capabilities of both the connected devices (host and device) and the cable.

The Pinout (Receptacle - Female Connector - Looking into the Connector)

The USB Type-C connector has 24 pins, arranged in two symmetrical rows of 12. The symmetry is what allows for reversibility. Here's a table and description:

Pin	Signal (Top Row - A)	Signal (Bottom Row - B)	Description
A1	GND	B12	Ground return. Essential for power and signal integrity.
A2	TX1+	B11	Transmitter differential pair 1, positive. Used for SuperSpeed USB data transmission (one direction).
A3	TX1-	B10	Transmitter differential pair 1, negative. Used for SuperSpeed USB data transmission (one direction).
A4	VBUS	B9	Power bus. Carries the main power supply voltage (typically 5V, but can be up to 20V with USB Power Delivery).
A5	CC1	B8	Configuration Channel 1. Used for connection detection, cable orientation detection, power delivery negotiation, and alternate mode configuration. One of these two pins (CC1 or CC2) will be pulled low by the cable to indicate orientation.
A6	D+	B7	USB 2.0 differential pair, positive. Used for USB 2.0 data transmission (half-duplex). Also used for some configuration signaling during connection.
A7	D-	B6	USB 2.0 differential pair, negative. Used for USB 2.0 data transmission (half-duplex). Also used for some configuration signaling during connection.
A8	SBU1	B5	Sideband Use 1. Used for alternate modes (e.g., DisplayPort AUX channel). Its specific function depends on the negotiated alternate mode.
A9	VBUS	B4	Power bus. Carries the main power supply voltage.
A10	RX2-	B3	Receiver differential pair 2, negative. Used for SuperSpeed USB data transmission (one direction).
A11	RX2+	B2	Receiver differential pair 2, positive. Used for SuperSpeed USB data transmission (one direction).
A12	GND	B1	Ground return.

Key Concepts and Explanations:

Reversibility: Notice how the pinout is mirrored (A1 = B12, A2 = B11, etc.). This symmetry is the key to the connector's reversibility. You can plug it in either way, and the internal circuitry figures out the orientation.

GND (Ground): Multiple ground pins provide a low-impedance return path for power and signals, crucial for signal integrity and preventing interference.

VBUS (Power Bus): These pins carry the main power supply. USB Type-C with Power Delivery (PD) can support much higher voltages and currents than older USB standards.

TX/RX Pairs (SuperSpeed): These are differential pairs used for high-speed data transmission in USB 3.x and 4. "Differential" means the signal is sent as the difference in voltage between the two wires, which makes it more resistant to noise. There are two pairs, allowing for simultaneous transmission and reception (full-duplex).

D+/D- (USB 2.0): These pins are used for backward compatibility with USB 2.0. They're also used for some initial configuration signaling when the connection is first made.

CC1/CC2 (Configuration Channel): These are critical pins. They are used for:

Connection Detection: Detecting when a cable is plugged in.

Orientation Detection: Determining which way the cable is plugged in (which side is "up"). This is done by measuring which CC pin is pulled low by a resistor in the cable.

Power Delivery Negotiation: Communicating between the host and device to negotiate the voltage and current levels for power delivery.

Alternate Mode Negotiation: Negotiating the use of alternate modes like DisplayPort or Thunderbolt.

SBU1/SBU2 (Sideband Use): These pins are used for auxiliary functions within alternate modes. For example, in DisplayPort mode, one of these pins is used for the AUX channel, which carries control and status information.

USB Power Delivery (USB PD) The CC pins negotiate the voltage and current. The VBUS pins carry the power. USB PD supports multiple power profiles, such as:

5V @ up to 3A (15W) - Default power

9V, 12V, 15V, 20V @ up to 5A (100W) - Standard Power Delivery

28V, 36V, 48V @ up to 5A (240W) - Extended Power Range (EPR), introduced with USB PD 3.1

Important Considerations:

Cable Matters: The cable itself plays a crucial role. A "full-featured" USB-C cable will have all the necessary wires connected. Simpler cables (e.g., charging-only cables) may omit some of the SuperSpeed data lines. The cable also contains resistors that identify its capabilities (e.g., maximum current).

Host and Device Capabilities: Not all USB-C ports support all features. A port might only support USB 2.0, or it might support USB 3.x and Power Delivery but not alternate modes. The capabilities of both the host and the device determine which pins are actually used.

Alternate Modes: When an alternate mode is active, the TX/RX pairs and SBU pins are repurposed to carry the signals for that mode (e.g., DisplayPort video signals). The CC pins are used to negotiate and manage the alternate mode.

Safety: Incorrectly wiring a USB-C connector, especially with Power Delivery, can damage devices. Always use certified cables and devices, and if you're working with the connector directly, be extremely careful.

Shielding: While not part of the 24 pin layout, the metal shell around the connector provides shielding. This metal shell is often connected to ground.

This detailed explanation should give you a thorough understanding of the USB Type-C female connector pinout and its various functions. Remember to always refer to the official USB-IF specifications for the most accurate and up-to-date information.
```