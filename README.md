# Power Electronics Bench

**Power Electronics Assignment 2**
Trishnika Sen · Roll No. 24EE10102

An interactive website for drawing power electronic circuits, simulating them, and viewing their waveforms.

## How to run

Open the HTML file in any web browser (Chrome, Edge, Firefox). It needs no installation and no internet connection.

## What to try

1. Pick a circuit from the **Example** menu, for example *Thyristor full-wave 3-phase bridge*.
2. Move the **Firing angle α** slider. The waveforms and results update immediately.
3. Press **Play**. The conducting devices light up on the schematic.
4. Scroll down to **Performance and theory** to compare the simulation with the textbook formula.

## Features

- **Schematic editor:** sources, R, L, C, diode, SCR, TRIAC, MOSFET/IGBT, probe and ground. Circuits can be built and edited freely.
- **17 ready circuits:**
  - single-phase and three-phase diode and thyristor rectifiers (half-wave, full-wave, semi-converter, freewheeling diode, RLE load)
  - thyristor-controlled reactor (TCR), AC voltage controller
  - buck and boost converters, full-bridge inverter
- **Waveforms:** time or ωt axis, gate-pulse and conduction timelines, zoom and cursor readout.
- **Results:** Vdc, Vrms, Idc, Irms, form factor, ripple factor, efficiency, input power factor, displacement factor, THD, harmonic spectrum and the conduction sequence table.

## Method

The circuit equations are solved at every time step (modified nodal analysis with backward-Euler integration). Diodes, thyristors and switches are modelled as switches with an on-resistance and a forward drop. Thyristors turn on with a gate pulse at α and turn off when their current reaches zero.

## Validation

All 17 circuits match the textbook formulas within 1.5%. The one exception is the boost converter at 3%, because the simulation includes the diode drop.

| Circuit | Theory | Simulated |
|---|---|---|
| 1-φ full converter, α = 45° | 146.4 V | 145.2 V |
| 3-φ 6-pulse bridge, α = 30° | 465.9 V | 463.9 V |
| TCR, α = 120° (fundamental current) | 5.73 A | 5.71 A |

## Limitations

- Devices switch instantly: no reverse recovery or switching losses.
- Sources are ideal unless a series resistance is given.
