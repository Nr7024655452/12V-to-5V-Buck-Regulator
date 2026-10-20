# 12V to 5V Buck Regulator (TPS56339)

A compact synchronous step-down (buck) converter PCB based on the Texas Instruments **TPS56339**, converting a 12 V input to a regulated 5 V output at up to 3 A.

## Specifications

| Parameter        | Value               |
|------------------|---------------------|
| Input voltage    | 12 V DC             |
| Output voltage   | 5 V                 |
| Output current   | 2 to 3 A            |
| Controller IC    | TPS56339DDCT        |
| Inductor         | 5.6 µH              |
| Input capacitors | 2 x 10 µF + 0.1 µF  |
| Output capacitors| 2 x 22 µF           |
| Connectors       | 2-pin screw terminals |

## Circuit Description

- **J1**: 12 V input screw terminal (with PWR_FLAG)
- **J2**: 5 V output screw terminal
- **U1 (TPS56339)**: Step-down converter IC
- **L1 (5.6 µH)**: Power inductor on the SW node
- **R4 / R5 / R6**: Feedback network setting the output voltage
- **R1 / R2**: Divider on EN pin (input undervoltage lockout)
- **C4 (0.1 µF) + R3**: Bootstrap capacitor and series resistor on the BOOT pin
- **C1, C2, C3**: Input capacitors
- **C5, C6**: Output capacitors

## Repository Structure


## Getting Started

1. Install [KiCad](https://www.kicad.org/) (v7 or later recommended)
2. Open `hardware/<project>.kicad_pro`
3. Generate Gerbers via **File → Fabrication Outputs → Gerbers**

## Usage

1. Connect a 12 V supply to **J1** (check polarity)
2. Measure 5 V at **J2**
3. Do not exceed the rated current without proper cooling

## Notes

- Verify the feedback resistor values against the TPS56339 datasheet for exactly 5.0 V output
- Keep the input capacitors close to the VIN and GND pins
- Keep the SW node and inductor trace short and wide

## Status

- [x] Schematic
- [x] PCB layout
- [ ] Prototype tested

## License

MIT License. See [LICENSE](LICENSE).

## Author

Nitin Rajput: [GitHub](https://github.com/NR7024655452)
