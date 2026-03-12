# Experiment 18 – Quadrature Phase Shift Keying (QPSK)

## Introduction

Quadrature Phase Shift Keying (QPSK) is a digital modulation technique derived from Binary Phase Shift Keying (BPSK). In BPSK, one bit of information is transmitted for every symbol. QPSK improves this by transmitting **two bits at the same time** using different phase states of the carrier signal.

In a QPSK system, the digital data stream is divided into two separate signals called the **even bits and odd bits**. Each of these signals modulates a carrier signal using BPSK. One carrier remains in its original phase while the other is shifted by **90°**, allowing the two signals to exist in the same bandwidth without interfering with each other.

The two modulated signals are then combined to produce the final QPSK signal. Because two bits are transmitted per symbol, QPSK makes more efficient use of the available bandwidth compared to BPSK.

In this experiment, the generation and analysis of the QPSK signal were performed using the **TIMS Online Simulator**. The simulator allowed the modules of the communication system to be connected virtually and the signals to be observed using the built-in oscilloscope.

---

## Objectives

- To understand the concept of **Quadrature Phase Shift Keying (QPSK)**.  
- To generate a QPSK signal using two BPSK-modulated carriers.  
- To observe how digital data is divided into even and odd bit streams.  
- To analyze the phase relationship between the carriers used in QPSK.  
- To use phase discrimination to isolate one of the BPSK components.

---

## Theory

Quadrature Phase Shift Keying works by transmitting two bits of information per symbol. The incoming digital data stream is first divided into two separate signals using a **serial-to-parallel converter**. 
One signal modulates a cosine carrier while the other modulates a sine carrier. Since sine and cosine signals differ by **90 degrees in phase**, both signals can be transmitted simultaneously without interfering with each other.
The two modulated signals are then added together to form the QPSK signal.

Mathematically, the QPSK signal can be written as:
s(t) = I(t)cos(2πfct) + Q(t)sin(2πfct)

where  

I(t) represents the in-phase component  
Q(t) represents the quadrature component  
fc represents the carrier frequency  

---

# Part A – Generating a QPSK Signal

In this part of the experiment, the QPSK signal was generated using the modules available in the **TIMS Online Simulator**. The oscilloscope in the simulator was first configured so that the digital signals and the modulated waveforms could be clearly observed. A digital data stream was then generated using the Sequence Generator module. This digital signal was passed through a Serial-to-Parallel Converter which separated the data into two signals representing the even and odd bits.

Each of these digital signals was then connected to a multiplier module to perform modulation. The Master Signals module provided two carrier signals in the form of sine and cosine waves, which are naturally **90 degrees out of phase**. Each multiplier used its digital input to modulate one of these carriers, producing two BPSK signals.

The outputs of the two multipliers were then combined using an Adder module to form the final QPSK signal. The waveform was observed on the oscilloscope to examine how the phase of the signal changed as the digital input varied.

### Observation

The waveform displayed noticeable phase changes corresponding to the digital input data. This confirmed that the two BPSK signals were successfully combined to create the QPSK signal.

---

## Question 1

**What is the relationship between the bit rate of the two digital signals and the bit rate of the Sequence Generator module's output?**

Answer  

Each of the two digital signals has **half the bit rate** of the original Sequence Generator output because the data stream is split into two parallel signals.

---

## Question 2

**What feature of the Multiplier’s output suggests that it’s a BPSK signal?**

Answer  

The carrier signal shows **180° phase reversals depending on the digital input**, which indicates that the signal is BPSK modulated.

---

## Question 3

**What type of signal is present on the Multiplier’s output?**

Answer  

The signal present is a **Binary Phase Shift Keying (BPSK) signal**, where the phase of the carrier changes according to the digital input data.

---

## Question 4

**According to the theory, what type of digital signal transmission is now present on the Adder’s output?**

Answer  

The signal at the adder output is a **Quadrature Phase Shift Keying (QPSK) signal**, which is formed by combining two BPSK signals that are 90° out of phase.

---

## Question 5

**Why is there only one sinewave when the QPSK signal is made up of two BPSK signals?**

Answer  

Both BPSK signals use the **same carrier frequency**, so when they are added together they appear as a single sinewave whose **phase changes depending on the combined digital data**.

---

# Part B – Using Phase Discrimination to Pick Out One of the QPSK Signal’s BPSK Signals

In this part of the experiment, phase discrimination was used to isolate one of the BPSK signals contained within the QPSK waveform. The circuit in the simulator was modified to implement a product detector using a multiplier module. The generated QPSK signal was applied to the multiplier along with a local carrier signal obtained from the Master Signals module.

A Phase Shifter module was used to adjust the phase of the local carrier so that it could align with one of the carrier signals used during modulation. The output of the multiplier was then passed through a Tuneable Low-Pass Filter to remove the high-frequency components and recover the baseband digital signal.

By slowly adjusting the phase of the local carrier and observing the signal on the oscilloscope, one of the digital data streams could be recovered from the QPSK signal.

### Observation

When the phase of the local carrier matched one of the original carriers, the recovered signal closely resembled the corresponding digital data stream. Changing the phase allowed the other data stream to be recovered.

---

## Question 6

Answer  

The multi-level signals appear when the phase of the local carrier is not aligned with the transmitted carrier. When the correct phase is reached, the recovered signal becomes a **two-level bipolar signal**. Two different phase settings can produce the correct bipolar output.

---

## Question 7

Answer  

The local carrier becomes **aligned in phase with one of the carriers used during modulation**, allowing that BPSK component to be recovered.

---

## Question 8

Answer  

After adjusting the phase further, the local carrier becomes aligned with the **other carrier component**, allowing the second BPSK signal to be recovered.

---

## Question 9

Answer  

The demodulator is considered only half of a full QPSK receiver because it can recover **only one of the two BPSK signals**. A complete QPSK receiver requires two demodulators to recover both data streams.

---

## Additional Notes

### Advantages of QPSK

- Transmits two bits per symbol, improving bandwidth efficiency compared to BPSK  
- Provides better spectral efficiency for digital communication systems  
- Widely used in modern wireless and satellite communication systems  

### Disadvantages of QPSK

- Receiver design is more complex compared to simpler modulation schemes  
- Requires accurate carrier phase synchronization for proper demodulation  
- Phase errors can lead to incorrect symbol detection  

### Applications

QPSK is commonly used in communication systems such as:

- satellite communication systems  
- digital television broadcasting  
- wireless communication networks  
- modern digital modulation systems including LTE and Wi-Fi

