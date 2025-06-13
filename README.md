# Silicon MRM Temperature Controller

## Project Description

This board is designed to stabilize the temperature of a silicon microring modulator (photonic chip) located on a separate board.  

The microring modulator (MRM) includes an integrated diode (used as a temperature sensor) and a resistive heater placed on top of the MRM. The diode voltage is read by this PCB through an ADC, and based on the measured temperature, the microcontroller adjusts the heater voltage via a DAC to maintain a stable operating temperature within the microring modulator.  

This control mechanism ensures stable photonic performance by compensating for thermal drift in the silicon microring modulator.

The PCB includes:
- ADC to read the diode voltage
- DAC to control the heater voltage
- Microcontroller to implement the control loop
- Supporting analog circuitry for signal conditioning

## Background and Motivation

Silicon microring modulators are highly susceptible to temperature variations. Although they can be highly efficient for light modulation, their strong temperature sensitivity often limits their practical use, as it can cause significant drift in their optical response.  

This project proposes a method to achieve precise thermal control of microring modulators by segmenting the microring, which is essentially composed of PN junction diodes used in reverse bias for light modulation. One of these segments is dedicated as a temperature sensor by operating it in forward bias. This approach makes it possible to directly monitor the exact temperature of the microring itself.  

To validate this idea, a segmented microring — previously designed — was used. The PCB designed in this project reads the voltage across this temperature-sensing diode segment of the microring and uses this information to actively control the temperature. An on-chip resistive heater is integrated on top of the microring, enabling precise temperature adjustments based on the sensed temperature shifts.

The diode segment used for temperature sensing produces very small currents, as the sensing element is physically very small (on the order of micrometers), and the temperature-induced voltage shifts are on the order of millivolts. Therefore, the control board must accurately detect voltage changes as small as 1 millivolt, requiring very low-noise analog signal paths and careful PCB design to minimize noise and interference throughout the system.  

The goal of this board is to provide highly stable and precise temperature control of the microring modulator by leveraging this integrated sensing mechanism and controlling the on-chip heater accordingly.

## Hardware Overview
Off-chip temperature controller block diagram featuring a
 single-diode temperature sensor. RF = 200kΩ, RG = 20kΩ, Rbias = 68kΩ,
 Vref = 0.8V fixed at 27◦C.
![image](https://github.com/user-attachments/assets/7a36e55b-2aef-49b6-8516-d50d4a32daed)
schematic
![image](https://github.com/user-attachments/assets/3cf93552-52d6-49ab-9a65-e37df3af9436)

layout
![image](https://github.com/user-attachments/assets/f28dd7c2-1460-4664-bbc9-b781c3b0df4f)

test setup diagram
![image](https://github.com/user-attachments/assets/49401800-e30d-4e04-9659-394e83ca79e9)
measurement
![image](https://github.com/user-attachments/assets/0e814b70-5dc5-424c-a913-1ecdc1e9252e)
after fabrication and soldered




