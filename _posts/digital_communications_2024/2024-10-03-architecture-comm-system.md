---
author: Dimitriy Georgiev
--- 
# Lecture Notes: Architecture of a Communication System

## System-Level Diagram of Radio Communication

### High-Level Diagram
- **Overview**: A communication system transforms data from the source to the sink through layered processing stages.

![Architecture of a Communication System](https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/arch-comm-system.drawio.svg)

## Component Breakdown

### Data Source
- **Definition**: The origin where data originates, constituting raw input for the communication system.
- **Types**: Examples include:
  - **Voice**: Captured from microphones.
  - **Video**: Sourced from cameras.
  - **Text**: Entered via keyboards.

### Source Encoder
- **Purpose**: Converts data into a more efficient form for transmission.
- **Functionality**: Employs data compression to minimize size without compromising essential information.
- **Techniques**:
  - **Huffman Coding**: Utilizes variable-length codes to encode frequent symbols efficiently.
  - **JPEG Compression**: Compresses image data using discrete cosine transformations and quantization.
  - **MPEG Compression**: Encodes video and audio by exploiting redundancy within and between frames.

### Channel Encoder
- **Purpose**: Augments data with redundancy to promote accurate transmission.
- **Functionality**: Facilitates error detection and correction.
- **Techniques**:
  - **Hamming Codes**: Offers basic error detection and correction capabilities.
  - **Reed-Solomon Codes**: Manages burst errors, widely applied in digital storage media like CDs/DVDs.
  - **Convolutional Codes**: Suitable for real-time error correction applications.

### Line Encoder
- **Purpose**: Transforms binary data into formats suitable for transmission through specific mediums.
- **Techniques**:
  - **Non-Return-to-Zero-Level (NRZ-L)**: Maintains constant voltage levels for binary 0 and 1.
  - **Non-Return-to-Zero-Mark (NRZ-M)**: Changes states upon each binary 1.
  - **Differential Non-Return-to-Zero (DNRZ)**: Encodes based on transitions between bits.
  - **Manchester Code**: Ensures sync by embedding a clock signal, flipping voltage mid-bit.

### Modulator
- **Purpose**: Encodes binary information into a carrier signal for transmission over the channel.
- **Types of Modulations**:
  - **Amplitude Modulation (AM)**: Modifies signal amplitude.
  - **Frequency Modulation (FM)**: Modifies signal frequency.
  - **Phase Modulation (PM)**: Modifies signal phase.

### Channel  
- **Types**:
  - **Wired Channels**: Includes twisted pairs, coaxial cables, and optical fibers.
  - **Wireless Channels**: Covers mediums like air, vacuum, and water.
- **Characteristics and Challenges**:
  - **Bandwidth**: Determines data transfer capacity.
  - **Attenuation**: Signal loss along the medium.
  - **Propagation Factors and Interference**: Environmental influences impacting signal integrity.

### Demodulator
- **Purpose**: Restores the modulated signal to its baseband form for processing.
- **Techniques**:
  - **Coherent Demodulation**: Precise with phase synchronization.
  - **Non-Coherent Demodulation**: Simpler, suitable when phase reference is unavailable.

### Channel Decoder
- **Functionality**: Detects and corrects errors within the received data.
- **Techniques**:
  - **Viterbi Algorithm**: Implements optimal decoding for convolutionally encoded signals.
  - **Other Decoding Techniques**: Depend on the initial coding employed.

### Source Decoder
- **Purpose**: Reverses source encoding, reconstructing the original data.
- **Examples**: Inverting compression formats like JPEG, MPEG to retrieve images, and videos.

### Data Sink
- **Definition**: The final destination of processed data.
- **Examples**: Monitors, speakers, and storage devices where the information is displayed or permanently stored.

## Case Study: Practical Radio Communication System

### Real-World System Example: DVB-S2
- **Breakdown**: Employs layered components echoing the communication architecture for stable broadcast over satellites.

### Receiver Architectures
- **Key Components**:
  - **LNA (Low-Noise Amplifier)**: Amplifies weak incoming signals.
  - **Bandpass Filter**: Allows only desired frequency bands.
  - **Mixer**: Translates frequencies for processing.
  - **LO (Local Oscillator)**: Provides reference signals for mixing.
- **Superheterodyne vs Direct Conversion Receivers**:
  - **Superheterodyne**: Uses intermediate frequencies for better selectivity and sensitivity.
  - **Direct Conversion**: Converts down to baseband directly, offering simplicity but with potential issues like DC offsets.
- **Contemporary Digital Receivers**: Integrated solutions using DSP for flexible and adaptive signal processing.