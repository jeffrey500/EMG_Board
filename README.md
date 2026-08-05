# Four Channel EMG AFE

This document outlines the design and design choices for the Analog Front End of an Four Channel Electromusclegram (EMG).

<img src="media/Board_3D.png" width="100%" alt="Board_3D">

## Main Features

Analog Front End:
- INA828IDR and OPA189IDR High Precision Instrumental and Operational Amplifiers
- Stage one 10x gain
- 10 Hz High Pass Filter
- Stage two 51x gain
- 400 Hz Low Pass Filter
- Total gain of 510x

Power:
- Low Noise and EMI SN6505 Push-Pull Transformer Setup
- 5000V of electrical isolation between input and AFE (medical grade)
- Ultra Low Noise and Ultra High Power Supply Rejection Ratio LT3094 and LT3042 Low Dropout Regulators

## SPICE
LTspice was utilized to verify the functionality of the Analog Front End. 
It should be noted that EMG signals range from 0-10mV peak-to-peak, 0-1.5mV RMS and have a frequency of 20-500Hz.
Filters should be used to attenuate signals outside the EMG range.

<img src="media/LTcircuit.png" width="80%" alt="LTcircuit">

### Frequency Response
Circuit Frequency Response from .01Hz to 10kHz. Note the first order 10 Hz High Pass and 400 Hz Low Pass Filters.

<img src="media/Frequency.png" width="80%" alt="Frequency">

### Transient Response
250ms transient response for a 100Hz 1mV sin wave with 200mV DC offset.

<img src="media/Transient.png" width="80%" alt="Transient">

## Schematic

### Analog Front End
<img src="media/Power_Sch.png" width="90%" alt="Power_Sch">

### Power
<img src="media/AFE.png" width="90%" alt="AFE">

### Top Sheet
<img src="media/Top.png" width="80%" alt="Top">

## Layer Stackup

| Layer | Purpose |
|-------|--------|
| 1     | Signal |
| 2     | Ground |
| 3     | Power  |
| 4     | Ground |

### Top Signal with Ground Pour
<img src="media/Top_Signal.png" width="80%" alt="Top_Signal">

### Power
<img src="media/Ground.png" width="80%" alt="Ground">

### Ground
<img src="media/Power.png" width="80%" alt="Power">

The top half contains the +5V net and the bottom half contains the -5V net.

### Bottom Ground
<img src="media/Bottom_Ground.png" width="80%" alt="Bottom_Ground">

## License
[EMG_Board](https://github.com/jeffrey500/EMG_Board) © 2026 by [Jeffrey Zhu](https://jzhu.ca) is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
