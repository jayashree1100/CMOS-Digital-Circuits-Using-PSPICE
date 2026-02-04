# ORCAD PSPICE Simulation & Waveform Guide

  In this section, the transient simulation procedure for a CMOS digital circuit using ORCAD PSPICE and the procedure to observe output  waveforms to verify logic functionality are described.

# CMOS Transient Simulation

## Simulation Tool
- **Software:** ORCAD PSPICE
- **Analysis Type:** Transient Analysis
- **Design Style:** Static CMOS logic using NMOS and PMOS transistors

## Simulation Procedure

### Simulation Step:
- Open ORCAD PSPICE and load the project containing the CMOS circuit schematic.
- Ensure NMOS and PMOS transistor models (enhancement type) are correctly assigned.
- Apply the DC power supply (VDD) to the circuit.
- Define input voltage sources for A, B, C, and D.
- Configure transient analysis with an appropriate simulation time and time step.

### Simulation Execution & Observation

- Place voltage probes at all input nodes (A, B, C, D) and at the output node (Y).
- Run the transient simulation.
- Observe the output waveform and verify that it follows the expected Boolean logic:
  `Y = (A(B + CD))'`

## Waveform Generation

- Output waveforms are observed using **PSPICE Probe** during transient analysis.
- Voltage waveforms include:
- **Input signals:** A, B, C, D
- **Output signal:** Y
- The observed waveforms demonstrate correct logic transitions based on the Boolean expression:
  `Y = (A(B + CD))'`

## Viewing & Interpreting Waveforms

- Waveforms are generated automatically during transient analysis.
  -  **logic HIGH (1)** corresponds to voltage ≈ VDD.
  -  **logic LOW (0)** corresponds to voltage ≈ 0 V.
- Verified the following:
  - Correct logic inversion
  - Full voltage swing
- Proper complementary switching of NMOS and PMOS transistors
- Waveform results are saved in the `waveforms/` directory for reference and documentation.

## Expected Simulation Results

- Output waveform matches the Boolean truth table.
- No static current flow occurs in steady-state conditions.
- Power dissipation occurs mainly during switching transitions.
- Static CMOS behavior is clearly demonstrated.

## Notes

- All transistors used are enhancement-type MOSFETs.
- Appropriate NMOS and PMOS sizing ensures clean output transitions and full voltage swing.
- This simulation validates both logic correctness and low-power CMOS operation.

