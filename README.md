# Silicon MRR Temperature Controller

## Project Description

This board is designed to stabilize the temperature of a silicon microring modulator (photonic chip) located on a separate board.  

The microring modulator (MRM) includes an integrated diode (used as a temperature sensor) and a resistive heater placed on top of the MMRM. The diode voltage is read by this PCB through an ADC, and based on the measured temperature, the microcontroller adjusts the heater voltage via a DAC to maintain a stable operating temperature within the microring modulator.  

This control mechanism ensures stable photonic performance by compensating for thermal drift in the silicon microring modulator.

The PCB includes:
- ADC to read diode voltage
- DAC to control heater voltage
- Microcontroller to implement the control loop
- Supporting analog circuitry for signal conditioning
