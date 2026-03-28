PCPU-NANO1 T4 — Documentation

**1-bit CPU built with 4 transistors, 7 resistors**

---

## 1. Specifications

| Parameter | Value |
|-----------|-------|
| Transistors | 4 x NPN (BC547 / 2N2222) |
| Resistors | 7 x 1kΩ |
| Power Supply | +5V |
| Instructions | 2 (NOP, NADJZ) |
| Inputs | INS, DATA, IN |
| Outputs | OUT, JMP |

---

## 2. Logic Truth Table

| INS | DATA | IN | OUT | JMP |
|-----|------|----|-----|-----|
| 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 1 |

---

## 3. Schematic

![Schematic](images/schematic.png)

---

## 4. Arduino Connection (Loader)

| Arduino Pin | PCPU Signal |
|-------------|-------------|
| Pin 2 | IN (optional) |
| Pin 3 | DATA |
| Pin 4 | INS |
| Pin 5 | JMP |
| Pin 6 | OUT |
| 5V | VCC |
| GND | GND |

---

## 5. Simple Program (Blinking)

| Address | INS | DATA | Description |
|---------|-----|------|-------------|
| 0 | 1 | 1 | NADJZ |
| 1 | 0 | 0 | NOP |
| 2 | 0 | 0 | NOP |
| 3 | 1 | 1 | NADJZ (jump to 0) |

---

## 6. Scaling to n Bits

Connect **n cores** in parallel:

| Signal | Connection |
|--------|------------|
| INS | common |
| DATA[i] | own bit |
| OUT[i] | own LED |
| JMP[i] | diode OR → common JMP |

---

## 7. Standalone System

| Component | Model |
|-----------|-------|
| Program Memory | 28C256 (32K×8) |
| Program Counter | 74HC161 |
| Clock Generator | NE555 |
| Registers (optional) | 74HC173 |

---

© 2026 — Open Documentation. Licensed under MIT License.
