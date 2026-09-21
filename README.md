# PIC Microcontroller Simulation Labs

Browser-based, cycle-accurate simulators for classic Microchip PIC microcontrollers — no compiler, no programmer, no installs. Open the HTML file and start writing assembly.

## What's included

| Simulator | Chip | Link |
|---|---|---|
| PIC16F877 Simulation Lab | PIC16F877 (40-pin, 4 register banks, 8K×14 Flash) | [Launch](https://claude.ai/artifact/QENMwShFuEUowECJ4RFzPK) |
| PIC16F84A Simulation Lab | PIC16F84A (18-pin, 2 register banks, 1K×14 Flash) | [Launch](https://claude.ai/artifact/Bw4e2LxvsEXsAvTNjKfBgE) |

Each lab is a single self-contained `.html` file — download it and open it directly in any modern browser, or host it with GitHub Pages (see below).

## Features

- **Two-pass assembler** for the mid-range PIC instruction set, with labels, literals and directives
- **Cycle-accurate execution core** — run continuously at a selectable clock speed (4/8/20 MHz) or step one instruction at a time from the CLI
- **Live virtual breadboard** — PORTB/PORTA pins drive LEDs, switches and a 7-segment display in real time
- **Interrupts** — real rising-edge INT vectoring, stack push, GIE clearing and RETFIE
- **TMR0 module** — prescaler, clock source selection and T0IF overflow, visualized from the datasheet's own timer block diagram
- **All SFRs and memory banks** visible and updating live, including the classic bank-switching gotchas (e.g. `MOVWF TRISB` / `MOVWF OPTION_REG` landing in the wrong register when `RP0` is set incorrectly)
- **Logic analyzer** — capture any pin over time, from 1 ms/div down to 1 ns/div
- **Command-line mode** — execute one instruction at a time and see its effect ripple through every related SFR and tab

## Getting started

1. Download the `.html` file for the chip you want to simulate.
2. Open it in your browser (double-click, or `File → Open`).
3. Load one of the built-in example programs, or write your own assembly in the editor.
4. Hit **Run** (or step through instructions from the CLI) and watch the registers, breadboard, timer and interrupt state update live.

No build step, no dependencies, no server required.

## Hosting on GitHub Pages

To give each simulator its own public URL:

1. Push the `.html` files to this repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, pick your branch and `/ (root)`, then **Save**.
4. GitHub publishes the site at `https://<your-username>.github.io/<repo-name>/`, and each simulator is reachable at that URL plus its filename, e.g. `.../PIC16F877_Simulation_Lab.html`.

## Why these exist

Bank switching, TRIS/PORT confusion, and interrupt bookkeeping are where most students learning these chips get stuck — usually with only a datasheet and a physical board to debug against. These labs make that state visible: every instruction's effect on the SFRs, memory banks and I/O is shown immediately, side by side with the register that actually changed (including when it's the *wrong* one).

## License

Educational use. No warranty — these are simulators, not a substitute for testing on real hardware.
