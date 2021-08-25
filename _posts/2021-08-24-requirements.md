## Project Definition - Ground Station Squad

Theoretical knowledge gives you a deeper understanding of a concept through seeing it in the context of understanding the why behind it.
Practical knowledge, on the other hand, can often lead to a deeper understanding of a concept through the act of personal experience.

The Space Challenges' program is structured in a way that combines both and allows the participants to perform at an exceptional level.
One of the projects in this year's edition challenged the participants to build a fully functional ground station and establish successful signal reception from one of EnduroSat's satellites.

---

### Ground Station Requirements


#### Mission

Successful reception of data from EnduroSat's QMR-KWT satellite via a SatNOGS ground station over UHF frequency range that captures 2 passes a day.

#### System

1. The system shall be connected to the SatNOGS network
2. The system shall process radio signals via an SDR
3. The system shall track orbiting satellites with a rotator
4. The system shall be able to capture low power signals from cube satellites
5. The system shall capture radio signals in the UHF frequency range

#### Subsystems

1. A Raspberry Pi shall be used as a SatNOGS client
2. A RTL2832U & R820T2 based SDR shall be used - e.g. Nooelec NESDR SMArt v4
3. A rotator should be build according to the SatNOGS Rotator v3 design
4. A wide-band LNA should be used to improve signal reception - e.g. Nooelec LaNa
5. A Yagi antenna should be build according to UHF specifications

