# LEGACY ALPHA EMU - ALPHA Playground

## Overview

The **LEGACY ALPHA EMU - ALPHA Playground** was a larger breakout-style emulator PCB designed for developing, testing, and experimenting with Honda OBD1 ECU emulation hardware.

The Playground was built around the idea of making a flexible development board for ECU emulator research using a standard 28-pin ROM socket and parallel memory interface. It was not designed as the final compact product form factor. Instead, it was created as a hardware development platform for testing buffer layouts, memory configurations, control signals, and emulator behavior on real ECU hardware.

This board was designed around the **RP2350B WeAct board**, continuing the ALPHA hardware direction after discontinuing the earlier STM32H7-based emulator line.

The ALPHA Playground is now considered **legacy hardware**, but it remains a useful reference tool for anyone developing an ECU emulator based around a 28-pin socket and parallel memory bus.

## Purpose

The purpose of the ALPHA Playground was to provide a larger, easier-to-probe emulator development PCB for testing different approaches to Honda OBD1 ROM emulation.

Instead of building a tiny final product board with limited debug access, the Playground exposed more hardware options and visual feedback so different emulator strategies could be tested quickly.

This made it useful for experimenting with address/data buffering, output enable behavior, write enable behavior, memory replacement timing, and different parallel memory devices.

## Hardware Platform

The ALPHA Playground was designed around the **RP2350B WeAct development board**.

The RP2350B platform became the preferred direction for ALPHA emulator revisions after the STM32H7 line was discontinued. The RP2350B provided a compact, powerful, and flexible microcontroller platform for working with parallel memory emulation, USB communication, and high-speed GPIO control.

The Playground continued that development direction by giving the RP2350B a larger experimental hardware base to work from.

## Design Features

The ALPHA Playground included multiple hardware features intended for emulator development and debugging.

```text
RP2350B WeAct based design
Larger breakout-style emulator PCB
Designed for Honda OBD1 28-pin ROM socket development
Parallel memory interface experimentation
Multiple LED indicators for signal and state feedback
Populated support for both 245 and 573 logic devices
Switch-selectable buffer configuration
Cypress NVRAM support
Expandable daughterboard interface
Optional SRAM sandwich board in place of NVRAM
Useful for testing emulator timing and signal behavior
Legacy development hardware
```

## 245 and 573 Buffer Testing

The Playground was populated to support both **245-style bus transceivers** and **573-style latches**.

Switches were included so either logic style could be selected and tested as part of the emulator signal path.

This allowed the board to be used for comparing different buffering strategies and understanding how each logic configuration affected ECU communication, ROM access, and emulator stability.

The ability to test both approaches on one board made the Playground especially useful during emulator development, where buffer direction, bus isolation, latch behavior, and timing all matter.

## LED Indicators

The ALPHA Playground included multiple LED indicators for visual feedback during testing.

These indicators were intended to make it easier to observe hardware states, control signals, and emulator activity without needing to immediately attach a logic analyzer or oscilloscope for every test.

The LED indicators helped during early bring-up, signal validation, and debugging.

## Cypress NVRAM Support

The board was designed with support for **Cypress NVRAM** devices.

Cypress NVRAM was used as a parallel memory target for ECU emulator development, allowing the emulator hardware to present ROM-like memory behavior to the ECU while still supporting fast updates and development workflows.

This made the Playground useful for testing memory access behavior in a real Honda OBD1 ECU environment.

## SRAM Daughterboard Expansion

In addition to the Cypress NVRAM setup, the Playground also included support for an expandable daughterboard.

This daughterboard was designed to sandwich an SRAM device in place of the NVRAM.

The purpose of this was to allow different memory strategies to be tested without fully redesigning the main emulator PCB. By using a daughterboard, SRAM-based emulator behavior could be evaluated while keeping the main Playground hardware platform intact.

## STM32H7 Line Discontinuation

Earlier ALPHA emulator development included STM32H7-based hardware.

That line was eventually discontinued in favor of RP2350B-based revisions.

The ALPHA Playground represents part of that transition. It was built after moving away from STM32H7 and toward the RP2350B platform for emulator development.

The RP2350B became the preferred platform for later ALPHA emulator revisions because of its flexibility, cost, availability, and suitability for high-speed parallel GPIO experimentation.

## Legacy Status

This project is considered **legacy hardware**.

The ALPHA Playground was never meant to be the smallest or most polished final emulator product. It was a development tool created to test ideas, validate hardware behavior, and explore different memory and buffer configurations.

Even though active development has moved forward, this board remains useful as a reference for anyone studying ECU emulator hardware based around:

```text
28-pin ROM sockets
Parallel memory buses
Address and data line buffering
Cypress NVRAM
SRAM replacement
RP2350B-based emulator designs
Honda OBD1 ECU memory behavior
```

The Playground is part of the ALPHA emulator development timeline and helped shape later ALPHA hardware direction.

## Educational Use

The files, designs, documentation, notes, and related information in this repository are provided for **educational and reference use only**.

This project is shared to help others learn about Honda OBD1 ECU emulator development, parallel memory hardware, RP2350B-based designs, logic buffering, latch/transceiver testing, NVRAM use, SRAM expansion, and 28-pin ROM socket emulator architecture.

You are responsible for verifying electrical compatibility, timing behavior, voltage levels, signal direction, memory device support, ECU compatibility, and safe operation before applying these designs to any ECU, vehicle, programmer, emulator, or hardware setup.

## Attribution Requirement

Any use, modification, redistribution, derivative hardware, documentation, video content, product listing, public project, or repository based on this design must provide clear attribution to:

```text
ALPHA / ALPHA Tuning
https://github.com/alpha-tuning
```

Attribution must remain visible in any public repository, documentation, schematic, PCB layout, board file, firmware reference, video description, product page, or derivative version that uses or references this work.

You may not remove ALPHA attribution, claim this design as your own original work, or present modified versions in a way that hides the original source.

If this project is used as the basis for another design, that design must clearly state that it is derived from the original LEGACY ALPHA EMU - ALPHA Playground hardware.

## Disclaimer

This repository is provided as-is, with no warranty, guarantee, or promise of fitness for any particular use.

Working with ECU emulator hardware can affect vehicle operation. Incorrect wiring, incorrect memory timing, unstable bus behavior, improper voltage handling, unsupported memory devices, invalid emulator firmware, or improper installation can cause ECU faults, drivability issues, hardware damage, or unsafe vehicle behavior.

Use these files and designs at your own risk.

## Project Status

Development on this hardware has ended.

The ALPHA Playground is considered legacy hardware.

Future ALPHA work is focused on modern real-time emulation platforms, including **ALPHAemu**, **AlphaLink**, and open-source related workflows such as **oneROM**.
