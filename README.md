# llm-usbc

## LLM interpretations of the USB-C specification

I came up with this idea as i was daydreaming about what i'd do to charge my laptop if i suddenly found myself stranded in the 1960s

Strange premise, but i realised i had a local LLM and ollama installed on my laptop! unfortunately it (llama3.2:3B) couldn't even get close to providing the pinout, let alone any other specs.

I've decided to concatenate responses from popular LLMs to see if *any* of them could provide something as simple as the pinout of a USB-C connector. LLMs being completely unable to answer (imo) very simple questions is why i *never* use them.

## The question

```
Provide the pinout of a female USB Type-C connector
```

## Scoring

### One point is granted for each correct specification

- [ ] Number of pins (24)
- [ ] VBUS and GND pins
- [ ] USB 2.0 pins
- [ ] All other pins

This gives us a 0-4 score on how useful a models' pinout would be if implemented. A score of 4 means the full USB Type-C spec could be implemented (as long as the necessary logic and microcontrollers are included on the connector itself)

## Pinout

### This is the "baseline" pinout we're looking for:

```
Pin|  Use | Use  |Pin
---|------|------|---
A12|  GND | GND  |B1    # Ground
A11| RX2+ | TX2+ |B2    # USB3.1 SS
A10| RX2- | TX2- |B3    # USB3.1 SS
 A9| VBUS | VBUS |B4    # Power
 A8| SBU1 | CC2  |B5    # CC2: PD / StS | SBU1: Sideband use
 A7|   D- | D+   |B6    # USB2
 A6|   D+ | D-   |B7    # USB2
 A5|  CC1 | SBU2 |B8    # CC1: PD / StS | SBU2: Sideband use
 A4| VBUS | VBUS |B9    # Power
 A3| TX1- | RX1- |B10   # USB3.1 SS
 A2| TX1+ | RX1+ |B11   # USB3.1 SS
 A1|  GND | GND  |B12   # Ground
```

## Scores

| Model | Score |
|-------|-------|
| anthropic/claude-3.5-sonnet | 4 |
| openai/gpt-4o | 4 |
| openai/gpt-4.5 | 4 |
| google/gemini-2.0-pro | 3 |
| google/gemini-2.5-pro | 3 |
| openai/gpt-5 | 3 |
| openai/gpt-5-mini | 3 |
| openai/gpt-5.2 | 3 |
| openai/gpt-o1 | 3 |
| openai/gpt-o1-mini | 3 |
| openai/gpt-o3-mini-high | 3 |
| deepseek/deepseek-r1:671b | 3 |
| openai/gpt-o3-mini | 2 |
| deepseek/deepseek-v3 | 2 |
| meta-llama/llama-3.3-70b-instruct | 1 |
| openai/gpt-4o-mini | 1 |
| deepseek/deepseek-r1:14b | 1 |
| google/gemini-2.0-flash | 1 |
| meta-llama/llama-3.2:3b | 0 |
| microsoft/phi-4:14b | 0 |
| meta-llama/llama-codellama:13b | 0 |
