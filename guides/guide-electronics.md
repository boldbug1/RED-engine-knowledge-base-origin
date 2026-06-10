# ⚡ Electronics: Knowledge Base

> Electricity doesn't forgive mistakes. Understanding it does.

---

## The Fundamentals

Everything in electronics comes down to three concepts and one law.

### Voltage (V)
**Electric potential difference.** The "pressure" that pushes electrons through a circuit. Measured in Volts.

### Current (I)
**Flow of electrons.** How much charge passes a point per second. Measured in Amperes (Amps).

### Resistance (R)
**Opposition to current flow.** Measured in Ohms (Ω).

### Ohm's Law

```
V = I × R
```

Rearranged:
- `I = V / R`  — more voltage OR less resistance = more current
- `R = V / I`  — knowing voltage and current tells you resistance

**Power:**
```
P = V × I     (Watts = Volts × Amps)
P = I² × R
P = V² / R
```

---

## Circuit Types

### Series Circuit
Components connected end-to-end in a single path.

```
[Battery] → [R1] → [R2] → [R3] → back
```
- Current is the same through all components.
- Voltage divides across components.
- Total resistance: `R_total = R1 + R2 + R3`

### Parallel Circuit
Components share the same two nodes.

```
[Battery] → [R1]
          → [R2]  → back
          → [R3]
```
- Voltage is the same across all components.
- Current divides between paths.
- Total resistance: `1/R_total = 1/R1 + 1/R2 + 1/R3`

---

## Core Components

### Resistor
Limits current. Color bands indicate value.

```
Brown-Black-Red-Gold = 1-0-×100 ±5% = 1000Ω (1kΩ)
```

### Capacitor
Stores charge temporarily. Releases it quickly. Used for filtering, decoupling, timing.
- Measured in Farads (F), typically µF or pF in practice.
- **Electrolytic capacitors are polarized** — wrong direction = explosion.

### Inductor
Stores energy in a magnetic field. Resists changes in current.
- Used in filters, power supplies, RF circuits.

### Diode
Allows current to flow in one direction only.
- **LED** (Light Emitting Diode): emits light when current flows.
- **Zener diode**: allows reverse flow at a specific breakdown voltage — used for voltage regulation.

### Transistor
The building block of modern computing. Acts as a switch or amplifier.

- **BJT** (Bipolar Junction Transistor): current-controlled. Types: NPN, PNP.
- **MOSFET** (Metal-Oxide-Semiconductor FET): voltage-controlled. Types: N-channel, P-channel.

**As a switch (MOSFET):**
```
Gate voltage HIGH → transistor ON → current flows from Drain to Source
Gate voltage LOW  → transistor OFF → no current flows
```

Modern CPUs contain **billions** of MOSFETs switching billions of times per second.

---

## Power Supplies

| Type | Description | Use |
|---|---|---|
| Linear regulator | Drops excess voltage as heat | Simple, low noise, low efficiency |
| Buck converter | Steps voltage down (switching) | Efficient, complex |
| Boost converter | Steps voltage up (switching) | Efficient, complex |
| LDO | Low dropout linear regulator | Clean power for analog/RF |

**Common voltages:**
- 3.3V — Modern microcontrollers, logic
- 5V — USB, legacy TTL logic, many sensors
- 12V — PC rails, motors, automotive
- 24V — Industrial, HVAC
- 48V — PoE, telecom

---

## Digital Logic

Modern electronics is built on **logic gates** — simple circuits that output based on input combinations.

| Gate | Symbol | Behavior |
|---|---|---|
| AND | `A · B` | Output HIGH only if A AND B are HIGH |
| OR | `A + B` | Output HIGH if A OR B is HIGH |
| NOT | `Ā` | Inverts input |
| NAND | `¬(A·B)` | AND then invert — universal gate |
| NOR | `¬(A+B)` | OR then invert — universal gate |
| XOR | `A ⊕ B` | HIGH only if inputs differ |

**NAND and NOR are "universal" gates** — any logic circuit can be built from only one of them.

---

## Microcontrollers

A microcontroller (MCU) is a small computer on a chip — CPU, RAM, flash memory, and I/O peripherals integrated.

**Popular platforms:**

| Platform | Core | Notes |
|---|---|---|
| Arduino Uno | ATmega328P (8-bit) | Beginner, 5V logic |
| ESP32 | Xtensa LX6 (32-bit) | WiFi + BT built in, very popular |
| STM32 | ARM Cortex-M | Professional grade, many variants |
| Raspberry Pi Pico | RP2040 (ARM M0+) | Cheap, dual-core, MicroPython |

**GPIO (General Purpose Input/Output):** Pins you can set HIGH or LOW, or read to detect signals.

---

## Communication Protocols

| Protocol | Type | Speed | Notes |
|---|---|---|---|
| UART/Serial | Async, 2-wire | ~1Mbps | Simple, universal debug |
| SPI | Sync, 4-wire | ~50Mbps | Fast, full-duplex |
| I²C | Sync, 2-wire | ~400kHz | Multi-device on 2 wires |
| USB | Serial | Up to 40Gbps | Complex, ubiquitous |
| CAN | Differential, 2-wire | 1Mbps | Automotive, industrial |

---

## Safety

- **Always discharge capacitors** before working on powered-off circuits — they retain charge.
- **Respect mains voltage (120V/240V AC).** It will kill you. If you're not sure, don't touch it.
- Use a **current-limiting resistor** with LEDs — bare LED + 5V = instant dead LED.
- **Ground yourself** when working with static-sensitive components (ESD kills chips silently).
- Check polarity on electrolytic caps and ICs before powering up.

---

## Useful Formulas Reference

```
Ohm's Law:          V = IR
Power:              P = VI = I²R = V²/R
Series resistance:  R = R1 + R2 + ...
Parallel resistance:1/R = 1/R1 + 1/R2 + ...
Capacitors series:  1/C = 1/C1 + 1/C2 + ...
Capacitors parallel:C = C1 + C2 + ...
RC time constant:   τ = RC (63% charge in 1τ, ~5τ to full)
```

---

*Every circuit is a puzzle. Every component has a reason. When something smokes, the reason was wrong.*
