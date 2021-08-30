## Space Challenges - Antenna Construction

Yagi antennas play an important role  in  various  modern  wireless communication  technologies,  because  of their properties like low cross polarization level,  moderate  gain  and  high  radiation  efficiency.

---

### Materials

|                Part                 | Qty | Unit of Measure | Comment |
|:-----------------------------------:|:---:|:---------------:|:-------------------:|
| Extendable Rod (2m)                 |  1  |       PCE       |         Boom        |
| Steel Threaded Rod (34.4 cm)        |  1  |       PCE       |    Driven Element   |
| Steel Threaded Rod (30.9 cm)        |  9  |       PCE       |       Directors     |
| Nut M6                              |  20 |       PCE       |                     |
| RF Coaxial Cable, SMA, 50 ohm, 15cm |  1  |       PCE       |                     |
| RF Coaxial Cable, SMA, 50 ohm, 60cm |  1  |       PCE       |                     |
| RF Coaxial Cable, SMA, 50 ohm, 1m   |  1  |       PCE       |                     |
| Solder Flux                         |  1  |       PCE       |                     |
| SMA Coaxial Connector Plug          |  1  |       PCE       |                     |
| Electrical Insulation Tape          |  1  |       PCE       |                     |


### Code

```py
from math import *
c = 3e8 # Speed of light [m/s]
G = 1.66

fmin, fmax = float(input( 'Minimum  frequency (MHz): ' )), float(input( 'Maximum frequency (MHz): ' ))
N = int(input( 'Number of directors: ' ))

f = ( fmax + fmin ) / 2s
wavelength = c / f / 100 # [cm]
R= round ( 105 / 100 * wavelength / 2 ) / 100
A = round( wavelength / 2 ) / 100
D = round( .9 * wavelength / 2 ) / 100
RA = round( wavelength / 4 ) / 100
AD = round( .28 * wavelength ) / 100
DD = round( wavelength / 3 ) / 100
L2 = round( wavelength / 2 ) / 100
B = round( RA + AD + DD * ( N - 1 ) + 10 ) / 100
Gain = round( 100 * G * ( N + 2 ) ) / 100

print(f'Optimized for frequency of {f}MHz\nLength of Reflector: {R}cm\nDriven element length: {A} cm\nDirector length: {D} cm\nSpacing between Reflector and Driven element: {RA} cm\nSpacing between Driven element and Director: {AD} cm\nSpacing between Directors: {DD} cm\nApproximate gain: {Gain} dBi\nLength of Boom: {B} m')
```

#### Results

<img src="https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/antenna-front.jpg" alt="antenna-front" width="400">
<img src="https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/antenna-top.jpg" alt="antenna-top" width="400">
