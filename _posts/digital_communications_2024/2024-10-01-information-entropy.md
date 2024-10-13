---
author: Dimitriy Georgiev
--- 
# Lecture Notes: Introduction to Information Theory and Communication Channels

## Definition and Significance

### What is Information?
- **Information** is the data communicated between systems to reduce uncertainty about potential outcomes.
- Claude Shannon introduced a mathematical framework for information through **entropy**, representing uncertainty's reduction upon receiving a message.

### Entropy: As the Opposite of Information
- **Entropy** quantifies unpredictability or disorder within a set of messages.
- The entropy $$ H(X) $$ for a random variable $$ X $$ with probabilities $$ P(x_i) $$ is defined as:

$$
H(X) = -\sum_{i=1}^{n} P(x_i) \log_2 P(x_i)
$$

- It sets the lower bound on the average number of bits required to encode messages from an information source.

### Significance
- **Data Compression**: Entropy determines how compressible a dataset is, influencing encoding schemes like Huffman coding.
- **Error Correction**: It helps design codes for correcting errors in transmitted data.
- **Cryptography**: High entropy ensures secure communications, making unauthorized message decoding difficult.
- **Efficient Communication System Design**: Fundamental for designing systems that optimize data rate and error reduction.

## Historical Background

### Key Innovations
- Information theory introduced essential concepts such as **entropy**, **redundancy**, and **channel capacity**, pivotal for communication systems' efficiency and optimization.

### "A Mathematical Theory of Communication" – 1948
- Published by Claude Shannon, this paper established the mathematical foundation of communication, including entropy, channel capacity, and how noise impacts message transmission.

## Communication Channels

### Description and Types of Channels
- **Channels**: Mediums through which information is transmitted from sender to receiver.
- **Types**:
  - **Wireless**: Employs radio waves, e.g., Wi-Fi, cellular.
  - **Wired**: Includes telephone lines, fiber optic cables.
  - **Satellite**: Facilitates long-range data transmissions.

### Characteristics of Communication Channels
- **Bandwidth**: Determines information transmission rate.
- **Noise Levels**: Represents unwanted signal alterations.
- **Interference Potential**: External signals causing disruptions.
- **Signal Degradation**: Represents decline in signal quality over distance.

### Analog vs. Digital Channels
- **Analog Channels**: Use continuous signals; examples include traditional telephone lines and AM/FM radio.
- **Digital Channels**: Employ discrete signals like binary data, providing better noise resistance and error management.

### Capacity of a Channel

#### Shannon-Hartley Theorem
- Describes maximum channel capacity $$ C $$ in the presence of noise:

$$
C = B \log_2(1 + \frac{S}{N})
$$

  where $$ B $$ is bandwidth, $$ S $$ is signal power, and $$ N $$ is noise power.

- Real-world factors like interference, multipath fading, and non-linearities reduce practical channel capacity.

## Messages and Signals

### Definition of a Message
- **Message**: Comprises a sequence of symbols representing information sent from a sender to a receiver.
- **Importance of Encoding**: Encoding ensures messages are interpreted correctly and minimizes errors during transmission.

### Types of Encodings
- **Text**: ASCII, Unicode
- **Voice**: PCM (Pulse Code Modulation)

## Entropy: The Measure of Uncertainty

### Definition and Examples
- Entropy relates to uncertainty, such as with a fair coin toss which has maximum entropy of $$ 1 $$ bit per toss.
- **Calculation Example**: For a fair coin, 

$$
H = -(0.5 \log_2 0.5 + 0.5 \log_2 0.5) = 1
$$

### Relationship and Impact
- **Entropy vs. Information**: High entropy implies less information, while low entropy signifies efficiently conveyed information.
- **Impact**: Guides data compression algorithms and transmission efficiency strategies.

## Numeric Bases in Information Theory

### Introduction to Number Bases
- **Decimal (Base 10)**: The standard numeric system.
- **Binary (Base 2)**: Used in digital systems, representing data with 0s and 1s.
- **Hexadecimal (Base 16)**: Provides a compact representation of binary data.

### Conversion Examples
- **Decimal to Binary**: $$ 10 $$ in decimal is $$ 1010 $$ in binary.
- **Binary to Hexadecimal**: $$ 1010 $$ in binary is $$ A $$ in hexadecimal.

### Binary System
- Preferred for digital devices due to its simplicity in logic operations (e.g., AND, OR, NOT gates) and enhanced fault tolerance.

## Practical Examples and Illustrations

### Binary Message Transmission
- **Encoding**: Text encoded using ASCII, e.g., character 'A' is represented as $$ 01000001 $$.
- **Binary Arithmetic**: Operations like binary addition are implemented through logic gates.

### Readings
*  [Introduction to EECS II: Digital Communication Systems, 6.02 Notes, Chapter 1: Introduction](https://ocw.mit.edu/courses/6-02-introduction-to-eecs-ii-digital-communication-systems-fall-2012/21992dcef7a08aa8b376a366d2979770_MIT6_02F12_chap01.pdf)
*  [Introduction to EECS II: Digital Communication Systems, 6.02 Notes, Chapter 2: Information, Entropy, and the Motivation for Source Codes](https://ocw.mit.edu/courses/6-02-introduction-to-eecs-ii-digital-communication-systems-fall-2012/4bcb4b872e8e98459ce71e77d4fe9c42_MIT6_02F12_chap02.pdf)
*  [Introduction to EECS II: Digital Communication Systems, 6.02 Notes, Chapter 4: Why Digital? Communication Abstractions and Digital Signaling](https://ocw.mit.edu/courses/6-02-introduction-to-eecs-ii-digital-communication-systems-fall-2012/4768bbb256ef6c9a3fd9330c2a124aca_MIT6_02F12_chap04.pdf)