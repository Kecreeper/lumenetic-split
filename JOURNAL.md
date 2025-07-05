---
title: "lumenetic-split"
author: "Eduardo"
description: "A split keyboard with large magnetic connectors for a charging hub featuring RGBW leds and large battery capacity."
created_at: "2025-07-01"
---

# July 4, 2025

## Background
I am starting this project with knowledge from hackpad, of making a keyboard pcb, and of making an nRF52840 circuit. Only the hackpad came to fruition, however.
When I made my full-size keyboard for hackboard, I felt that I didn't have as many features as I wanted due to the part budgets so I decided not to submit it and rather use Highway to make a split keyboard.
I began Highway with making an nRF52840 dev board with the same form-factor and pinout as the nice!nano, however halfway through the project, I felt that this was an unnecesarily expensive and unoriginal devboard that had already taken nearly a month. 

## The keyboard
This keyboard will be a split keyboard with large magnetic connectors inspired by the Joycon 2 connectors using pogo pins to connect to a charging hub that can connect both keyboards together. It will also feature a LED bar above the keys made possible by a 18650 battery. I will also consider adding rotary encoders and a joystick. The keyboard itself will have similar layout to the ZSA Voyager.

## Choosing a microcontroller module
First I had to choose between the E73-2G4M08S1C and the MDBT50Q-1MV2, two nRF52840 SMD modules that were basically the same price on [AliExpress](https://www.aliexpress.us/item/3256807191960642.html) and [DigiKey](https://www.digikey.com/en/products/detail/raytac/MDBT50Q-1MV2/13677591) at ~$6.
<img alt='E73' src='./imagesJournal/E73.png' width='250'>
<img alt='MDBT50Q' src='./imagesJournal/MDBT.png' width='250'>
> E73 on the left, MDBT50Q on the right

The MDBT50Q had only pads under it which were tiny. The E73 had castellated holes making it easier to solder, however it still had pads under it, but they were bigger than the MDBT50Q's pads. I chose the E73 because it was the easiest to solder and I can figure out a way to make them easy to solder or not use them at all.

## First schematic

Given my knowledge of nRF52840 circuits after my previously attempted project, the nRF was easy to wire on the schematic as the module already came with all the decoupling capacitors (excl. VBUS), inductors, the 32MHz crystal, and the antenna. All I had to add was the VBUS capacitor and an inductor to enable DC/DC mode on REGOUT0. I omitted the 32KHz crystal because it only gives a minimal battery life boost.

For now, I have made the matrix and USB C port on the schematic and some of the keys on the PCB.
![July 4 Schematic](/imagesJournal/July4Schematic.png)
![July 4 PCB](/imagesJournal/July4PCB.png)

**Total time spent: 4h**