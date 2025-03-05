# Gemini 2.0 Flash


## Results

- [x] Number of pins (24)
- [ ] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

## LLM Pinout

```
Pin|    Use | Use    |Pin (##)
---|--------|--------|--------
 A1| GND    | GND    |B1 [sic] # Ground
 A2| SSTXp  | SSTXp  |B11    # SuperSpeed Transmit Positive (Differential pair)
 A3| SSTXn  | SSTXn  |B10    # SuperSpeed Transmit Negative (Differential pair)
 A4| VBUS   | VBUS   |B9     # USB Power (typically 5V, but can be higher for USB Power Delivery)
 A5| CC1    | CC1    |B5     # Configuration Channel 1 (orientation detection, power negotiation)
 A6| D+     | D+     |B6     # USB 2.0 Data Positive
 A7| D-     | D-     |B7     # USB 2.0 Data Negative
 A8| SBU1   | SBU1   |B8     # Sideband Use 1 (Auxiliary signals, DisplayPort, etc.)
A10| SSRXn  | SSRXn  |B3     # SuperSpeed Receive Negative (Differential pair)
A11| SSRXp  | SSRXp  |B2     # SuperSpeed Receive Positive (Differential pair)
A12| GND    | GND    |B1     # Ground
```
It failed in some subtle ways, one of the big issues with LLMs in general!
For example, pin A6 should be Pin B7, and A7 -> B6.

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector

Okay, here's the pinout of a female USB Type-C connector, along with important notes and considerations.

USB Type-C Connector Pinout (Female)

The connector has 24 pins, arranged in two rows of 12. It's symmetrical, but the signals are not symmetrical. Therefore, the CC (Configuration Channel) pins are crucial for determining the orientation.

A1  A2  A3  A4  A5  A6  A7  A8  A9 A10 A11 A12
   ----------------------------------------------------
   | G | SS_TXp | SS_TXn | VBUS | CC1 | D+  | D-  | SBU1| VBUS|SS_RXn|SS_RXp| G |
   ----------------------------------------------------
   | G | SS_RXp | SS_RXn | VBUS | CC2 | D+  | D-  | SBU2| VBUS|SS_TXn|SS_TXp| G |
   ----------------------------------------------------
      B1  B2  B3  B4  B5  B6  B7  B8  B9 B10 B11 B12


Pin Definitions:

Pin	Name	Description
A1/B1	GND	Ground
A2/B11	SSTXp/SSTXp	SuperSpeed Transmit Positive (Differential pair)
A3/B10	SSTXn/SSTXn	SuperSpeed Transmit Negative (Differential pair)
A4/B9	VBUS	USB Power (typically 5V, but can be higher for USB Power Delivery)
A5	CC1	Configuration Channel 1 (orientation detection, power negotiation)
B5	CC2	Configuration Channel 2 (orientation detection, power negotiation)
A6/B6	D+	USB 2.0 Data Positive
A7/B7	D-	USB 2.0 Data Negative
A8	SBU1	Sideband Use 1 (Auxiliary signals, DisplayPort, etc.)
B8	SBU2	Sideband Use 2 (Auxiliary signals, DisplayPort, etc.)
A10/B3	SSRXn/SSRXn	SuperSpeed Receive Negative (Differential pair)
A11/B2	SSRXp/SSRXp	SuperSpeed Receive Positive (Differential pair)
A12/B1	GND	Ground

Important Notes and Considerations:

Symmetry, but Not Signal Symmetry: While the connector is physically symmetrical, the signals are not interchangeable between rows. The CC pins determine the cable orientation, and the host/device will adapt accordingly.

SuperSpeed Data: The SS_TX and SS_RX pairs are for USB 3.x (SuperSpeed) data transfer. These are differential pairs, requiring careful impedance matching and routing in high-speed designs.

USB 2.0 Data: The D+ and D- pins are for USB 2.0 data transfer. These also form a differential pair. USB 2.0 is supported for backwards compatibility.

VBUS: VBUS provides power. The standard USB 2.0/3.0 voltage is 5V. USB Power Delivery (USB-PD) allows for higher voltages (up to 20V) and higher currents, enabling faster charging and powering of more demanding devices.

CC1 and CC2 (Configuration Channel): These pins are critical. They are used for:

Cable Orientation Detection: The host/device detects which CC pin is pulled down through a resistor in the cable. This tells it which orientation the cable is plugged in.

Role Detection (Host/Device): The Rp/Rd resistor combinations on the CC pins determine the roles of the devices connected. A host typically uses Rp pull-up resistors, while a device typically uses Rd pull-down resistors.

USB Power Delivery (USB-PD) Negotiation: The CC pins are also used for communication related to USB Power Delivery, allowing devices to negotiate higher voltages and currents.

SBU1 and SBU2 (Sideband Use): These pins are used for alternate modes, such as DisplayPort (DisplayPort Alternate Mode) or Thunderbolt. The specific function depends on the implementation.

Resistors for CC1/CC2 (Rp and Rd):

Rp (Pull-up resistor): A resistor connected between VBUS and the CC pin. It signals the host capability to supply power. A host uses this to indicate the source current capabilities (e.g. Default USB Power, 1.5A, 3A).

Rd (Pull-down resistor): A resistor connected between the CC pin and ground. A device uses this to indicate its desire to sink power.

USB Power Delivery (USB-PD): This is a complex protocol that uses the CC lines to negotiate power delivery.

Hot Plugging: The USB Type-C connector is designed for hot plugging (connecting/disconnecting devices while powered).

PCB Layout: For high-speed data transfer (USB 3.x and above), careful PCB layout is essential. Differential pairs (SS_TX and SS_RX) should be routed with controlled impedance, minimal stubs, and matched lengths. Proper grounding is also crucial.

Connectors: There are many different USB Type-C connector manufacturers and styles (through-hole, surface mount, mid-mount, etc.). Choose a connector that is appropriate for your application and PCB design.

Cable Quality: The quality of the USB Type-C cable is crucial, especially for USB-PD and high-speed data. Poor quality cables can cause unreliable operation or even damage.

Practical Considerations for Designers:

Orientation Awareness: Your design must handle the cable being plugged in either way. The microcontroller/logic must be able to detect the CC pin state and adjust accordingly.

Power Delivery: If you are implementing USB-PD, you will need a USB-PD controller IC to handle the negotiation and power management.

Alternate Modes: If you are supporting alternate modes like DisplayPort, you will need appropriate hardware and software to handle those protocols.

ESD Protection: Consider ESD (Electrostatic Discharge) protection on the data lines (D+, D-, SS_TX, SS_RX) to prevent damage from electrostatic discharge events.

Testing: Thoroughly test your USB Type-C implementation to ensure it meets the USB specifications and works reliably with a variety of devices and cables.

This information should give you a comprehensive understanding of the USB Type-C connector pinout and its key features. Remember to consult the official USB specifications for the most detailed and up-to-date information. Good luck!
```