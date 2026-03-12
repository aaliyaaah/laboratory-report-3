# Experiment 15 – Amplitude Shift Keying (ASK)

## Introduction

In digital communication systems, information is transmitted by modifying certain properties of a carrier signal. One method used for this purpose is **Amplitude Shift Keying (ASK)**, where the amplitude of a carrier signal is varied according to a digital data sequence. ASK can be considered a digital form of amplitude modulation in which the carrier is switched on and off depending on the binary input signal.

In communication systems, it is important to efficiently share a communication channel among multiple users. Techniques such as **Time Division Multiplexing (TDM)** and **Frequency Division Multiplexing (FDM)** allow signals from different users to share the same communication medium. In FDM systems, each signal is transmitted using a different carrier frequency. ASK is one of the modulation techniques that can be used to transmit digital data using such carriers.

In this experiment, an ASK signal was generated using the modules available in the **TIMS online simulator**, which replicates the functionality of the Emona Telecoms-Trainer system in a virtual environment. A digital signal was used to control the presence or absence of the carrier. The ASK signal was then demodulated using an **envelope detector** to recover the transmitted data. Finally, a **comparator circuit** was used to restore the recovered digital signal into a clean digital waveform.

---

## Objectives

- To understand the concept of **Amplitude Shift Keying (ASK)**.
- To generate an ASK signal using a digital signal and carrier.
- To demodulate the ASK signal using an envelope detector.
- To restore the recovered digital signal using a comparator.
- To observe the effect of noise on ASK communication signals.

---

## Theory

Amplitude Shift Keying is a digital modulation technique where the **amplitude of a carrier wave changes according to the digital data** being transmitted.

Binary data is represented as:

- Logic **1** → Carrier present  
- Logic **0** → Carrier absent  

This form of ASK is also known as **On-Off Keying (OOK)**.

Mathematically, an ASK signal can be represented as:

s(t) = m(t) cos(2πfct)

where:

- m(t) = digital data signal  
- fc = carrier frequency  

When the digital signal is high, the carrier is transmitted. When the signal is low, the carrier is turned off.

---

# Part A – Generating an ASK Signal

In this part, an ASK signal was generated using the modules available in the **TIMS online simulator**. The digital signal was produced by the **Sequence Generator module**, while the carrier signal was obtained from the **Master Signals module**.

The digital signal controlled a **Dual Analog Switch**, which determined whether the carrier was connected to the channel output. When the digital signal was high, the carrier passed through the switch, and when it was low, the carrier was blocked.

### Procedure

1. Open the **TIMS online simulator** and load the required modules.
2. Configure the oscilloscope to observe both the digital signal and the ASK signal.
3. Set the oscilloscope trigger source and coupling to obtain a stable waveform display.
4. Set the input coupling of both oscilloscope channels to **DC**.
5. Adjust the oscilloscope time base to approximately **2 ms/div** for clear observation of the signals.
6. Connect the Sequence Generator, Master Signals module, and Dual Analog Switch according to the required configuration.
7. Observe the digital signal and the resulting ASK waveform on the oscilloscope display.

## Results

<p align="center">
<img src="https://github.com/user-attachments/assets/0d91a955-d5b9-48fe-a6d9-b44726cb5c10" width="400">
<br>
<b>Figure 15.1</b> Noise waveform observed on the oscilloscope.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/1f199500-3c72-43b1-b2e6-357592f2dc61" width="400">
<br>
<b>Figure 15.2</b> Noise signal with adjusted oscilloscope settings.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/0f67bd1a-c854-4e2e-bea5-e1bbfe4c72a7" width="400">
<br>
<b>Figure 15.3</b> Part A waveform observed using 2 ms/div timebase.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/5ce42aab-e8bc-4c78-b4e7-9f5d3ece095a" width="400">
<br>
<b>Figure 15.4</b> Signal observation during Part A Step 13 adjustments.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/158dcc44-a443-4ed7-a816-35ecf82e7891" width="400">
<br>
<b>Figure 15.5</b> Final waveform obtained after completing Part A.
</p>

---

## Question 1

**What is the relationship between the digital signal and the presence of the carrier in the ASK signal?**

Answer:

The carrier signal is present when the digital signal is logic **1**, and it disappears when the digital signal is logic **0**. The digital signal therefore controls whether the carrier is transmitted or not.

---

# Part B – Demodulating the ASK Signal

The ASK signal can be demodulated using an **envelope detector**. Since ASK is a form of amplitude modulation, the digital data can be recovered by detecting the signal envelope.

The envelope detector consists of:

- a **rectifier**
- a **low-pass filter**

### Procedure

1. Locate the **Tuneable Low-pass Filter module** in the simulator.
2. Set the **Gain control fully clockwise**.
3. Adjust the **Cut-off Frequency control** to the appropriate level.
4. Modify the circuit in the simulator to include the envelope detector.
5. Observe the output waveform of the envelope detector using the virtual oscilloscope.

### Result

The recovered signal resembles the original digital waveform but may appear **slightly distorted or smoothed** due to the filtering process.

<p align="center">
<img src="https://github.com/user-attachments/assets/eb92a9c6-1500-4486-a2ec-3d66067faffd" width="400">
<br>
<b>Figure 15.6</b> Part B – Final waveform after completing the procedure.
</p>

---

# Part C – Restoring the Recovered Digital Signal

Because the envelope detector output may contain slow rising edges and distortions, a **comparator circuit** is used to restore the signal.

A comparator converts the recovered analog waveform into a **clean digital signal with sharp transitions**.

### Procedure

1. Modify the circuit in the simulator to include the **Comparator module**.
2. Adjust the **Variable DC reference level** to approximately the middle of the signal amplitude.
3. Observe both the recovered signal and the comparator output on the oscilloscope.
4. Compare the restored digital signal with the original digital input.

## Result
<p align="center">
<img src="https://github.com/user-attachments/assets/be6e94ac-28b8-4bd3-9909-555ef7f4c97e" width="400">
<br>
<b>Figure 15.7</b> Part C – Final waveform observed after completing Step 20.
</p>

---

## Question 6

**How does the comparator turn the slow rising voltages of the recovered digital signal into sharp transitions?**

Answer:

The comparator compares the input signal with a reference voltage. When the input exceeds the reference level, the output switches rapidly to a high level, and when it falls below the reference level, the output switches to a low level. This creates sharp transitions that restore the digital waveform.

---

# Effect of Noise

In practical communication systems, signals are often affected by **noise**, which consists of unwanted electromagnetic interference. Noise can distort the ASK signal during transmission.

Noise sources may include:

- atmospheric radiation  
- electronic devices  
- other communication systems  

In this experiment, noise was simulated in the **TIMS online simulator** using a noise generator module.

The noise was added to the signal through an **adder module**, producing a noisy communication channel similar to real transmission environments.

### Observation

As the noise level increased:

- the ASK waveform became more distorted
- envelope detection became less reliable
- the recovered digital signal began to contain errors

If the noise level became too high, the receiver was no longer able to correctly recover the transmitted data.

---

# Conclusion

This experiment demonstrated how digital information can be transmitted using **Amplitude Shift Keying (ASK)**. Using the **TIMS online simulator**, an ASK signal was generated by switching a carrier signal according to a digital input signal. The signal was then demodulated using an envelope detector, and a comparator was used to restore the digital waveform.

The experiment also showed how noise affects communication systems. As the noise level increased, signal recovery became more difficult, highlighting the importance of proper signal processing techniques in digital communication systems.

---

# Additional Notes

### Advantages of ASK

- Simple implementation  
- Easy demodulation  
- Suitable for low-cost communication systems  

### Disadvantages of ASK

- Highly sensitive to noise  
- Lower reliability compared to PSK or FSK  

### Applications

ASK is used in:

- RFID systems  
- optical communication systems  
- remote keyless entry systems  
- low-cost wireless communication devices
