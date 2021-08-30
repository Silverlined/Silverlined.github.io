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

### Design

- Minimum frequency (MHz): 435 
	- Maximum frequency (MHz): 438 
	- Number of directors: 8 
	- Optimized for frequency of 436.5MHz 
	- Length of Reflector: 36.08cm 
	- Driven element length: 34.36 cm (a folded dipole antenna has 4 times higher impedance compared to a non-folded dipole; for space applications lower impedance of 50ohms is preferred using a non-folded/linear dipole)
	- Director length: 30.93 cm 
	- Spacing between reflector and driven element: 17.18 cm 
	- Spacing between driven element and director: 19.24 cm 
	- Spacing between directors: 22.91 cm 
	- Approximate gain: 16.6 dBi (-3dBi) 
	- Length of boom: 2.1 m
	- Balun: e.g. RG174 (Velocity of propagation Vc=0.66)
	- Wavelength WL = 69cm
	- L1 = 11.4cm
	- L2 = 34.2cm

#### Results

<img src="https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/antenna-front.jpg" alt="antenna-front" width="400">
<img src="https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/antenna-top.jpg" alt="antenna-top" width="400">
