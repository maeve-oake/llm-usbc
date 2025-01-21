# Llama 3.2 3b

Meta's Llama 3.2 goes small with 1B and 3B models.

## Results

WIP.

## LLM Pinout

I couldn't come up with a pinout based on what the model has provided - it's too incoherent.

The model seems to think that a USB-C connector has two 48 pins, but doesn't provide info for all of them

## Raw LLM output

```
>>> Provide the pinout of a female USB Type-C connector
The pinout of a female USB Type-C connector consists of two rows of pins, each with 24 
contacts. Here is the detailed pinout:

Row 1 (Top Row):

* Contact 1: Ground (GND)
* Contact 2: Power (+) VDD
* Contact 3-11: Alternate modes and interfaces (e.g., DisplayPort, Power Delivery, etc.)
* Contact 12-15: USB Alternate Mode (ALT)
* Contact 16-18: USB Power Delivery (PD)

Row 2 (Bottom Row):

* Contact 19: Ground (GND)
* Contact 20-23: Alternate modes and interfaces (e.g., DisplayPort, Power Delivery, etc.)
* Contact 24-27: USB Alternate Mode (ALT)
* Contact 28-30: USB Power Delivery (PD)

Note:

* Contacts 1-15 on both rows are the same as in USB Type-A connectors.
* The remaining contacts are used for specific USB Type-C features and interfaces.
* The exact pinout may vary depending on the specific use case or device, but this is the 
standard pinout for a female USB Type-C connector.
```