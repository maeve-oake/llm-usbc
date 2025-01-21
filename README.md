# llm-usbc

## LLM interpretations of the USB-C specification

This idea came up as i was daydreaming about what i'd do to charge my laptop if i suddenly found myself stranded in the 1960s

Strange premise, but i realised i had a local LLM and ollama installed on my laptop! unfortunately it (llama3.2:3B) couldn't even get close to providing the pinout, let alone any other specs.

I've decided to concatonate responses from popular LLMs to see if *any* of them could provide something as simple as the pinout of a USB-C connector. LLMs being completely unable to answer (imo) very simple questions is why i *never* use them.

## The question

```
Provide the pinout of a female USB Type-C connector
```

## Scoring

### One point is granted for each correct specification

- [ ] Number of pins (24)
- [ ] GND pins (A1, A12, B1, B12)
- [ ] VBUS pins (A4, A9, B4, B9)
- [ ] USB 2.0 Pins (A6, A7, B6, B7)
- [ ]

## Pinout

### This is the "baseline" pinout we're looking for:

```
 A1|  GND   GND  |B12   # Ground
 A2| TX1+   RX1+ |B11   # USB3.1 SS
 A3| TX1-   RX1- |B10   # USB3.1 SS
 A4| VBUS   VBUS |B9    # Power
 A5|  CC1   SBU2 |B8    # CC1: PD / StS | SBU2: Sideband use
 A6|   D+   D-   |B7    # USB2
 A7|   D-   D+   |B6    # USB2
 A8| SBU1   CC2  |B5    # CC2: PD / StS | SBU1: Sideband use
 A9| VBUS   VBUS |B4    # Power
A10| RX2-   TX2- |B3    # USB3.1 SS
A11| RX2+   TX2+ |B2    # USB3.1 SS
A12|  GND   GND  |B1    # Ground
```
