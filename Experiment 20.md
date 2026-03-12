# Experiment 20 – Undersampling in Software Defined Radio (SDR)

## Introduction

Software Defined Radio (SDR) is a communication system where many signal processing tasks traditionally performed by hardware are instead implemented using software. In SDR systems, radio frequency signals are first converted into digital form and then processed by software algorithms to perform demodulation and decoding.

One important concept used in SDR systems is **undersampling**, also known as **band-pass sampling**. Normally, according to the Nyquist sampling theorem, a signal must be sampled at least twice its highest frequency to avoid aliasing. However, for band-limited signals that do not contain frequencies near DC, it is possible to sample at rates lower than the carrier frequency while still recovering the original information.

This experiment demonstrates how undersampling can be used to demodulate a modulated signal directly. A DSBSC signal is generated first, and then a sample-and-hold circuit together with a low-pass filter is used to recover the message signal through undersampling. The experiment also investigates the effects of synchronization errors between the sampling signal and the carrier.

---

## Objectives

- To understand the principle of undersampling in software defined radio systems.
- To generate a DSBSC signal using a multiplier module.
- To observe the effects of sampling a band-limited signal.
- To recover the original message signal using undersampling.
- To study the effect of synchronization errors between sampling frequency and carrier frequency.

---

## Theory

Undersampling allows a band-limited signal to be sampled at a rate lower than twice its carrier frequency while still preserving its information. When a signal is sampled, multiple frequency components called aliases are produced. If the sampling frequency is chosen properly, one of these aliases can fall within the baseband region, effectively translating the signal to a lower frequency.

In communication systems, this means that a high-frequency modulated signal can be directly converted to baseband using a sampling process rather than traditional mixing or product detection. After sampling, a low-pass filter can be used to remove unwanted high-frequency components and recover the original message.

However, successful demodulation using undersampling requires proper synchronization between the sampling signal and the modulated carrier. Even small frequency or phase errors can affect the recovered signal.

---

# Part A – Setting up a Bandwidth-Limited Signal

In this part of the experiment, a DSBSC signal was generated to serve as the bandwidth-limited signal for undersampling.

### Procedure

Using the **TIMS Online Simulator**, the communication modules were connected according to the configuration shown in the experiment diagram. The Master Signals module generated a **2 kHz sinewave message**, while a **100 kHz carrier signal** was also taken from the Master Signals module.

Both signals were applied to the Multiplier module to produce a **DSBSC signal**. The oscilloscope was configured to display the message signal on Channel 1 and the modulated signal on Channel 2. The timebase and scaling controls were adjusted until several cycles of the message signal could be clearly observed.

The DSBSC signal produced by the multiplier showed alternating halves of its envelope that followed the shape of the original message signal.

### Result
<p align="center">
<img src="https://github.com/user-attachments/assets/150dc5de-5801-4eab-94b4-776074f0fa77" width="400">
<br>
<b>Figure 20.1</b> Part A – Signal observation during Step 6.
</p>

---

### Question 1  
**For the given inputs to the Multiplier module, what are the frequencies of the two sinewaves that make up the DSBSC signal?**

**Answer:**

Carrier frequency = 100 kHz  
Message frequency = 2 kHz  

DSBSC produces two sidebands:

- Upper Sideband = **102 kHz**
- Lower Sideband = **98 kHz**

---

### Question 2  
**What’s the bandwidth of the DSBSC signal?**

**Answer:**

Bandwidth = Upper sideband − Lower sideband  

Bandwidth = 102 kHz − 98 kHz  

**Bandwidth = 4 kHz**

---

# Part B – Direct Down-Conversion Using Undersampling

In this section, undersampling was used to demodulate the DSBSC signal. A sample-and-hold circuit and a baseband low-pass filter were used to recover the original message signal.

### Procedure

The circuit configuration was modified to include the **Sample-and-Hold module** controlled by a digital sampling signal from the Master Signals module. The DSBSC signal was applied to the input of the Sample-and-Hold module, while the sampling signal provided the control input.

The output of the Sample-and-Hold circuit produced an undersampled version of the DSBSC signal. This signal was then passed through the **Baseband Low-Pass Filter**, which removed higher-frequency components and allowed the recovered message signal to be observed on the oscilloscope.

The undersampled signal was compared with the original message signal to observe how undersampling effectively shifted the signal into the baseband region.

### Results
<p align="center">
<img src="https://github.com/user-attachments/assets/b7380390-11d8-44ad-95bb-96ac60a325c6" width="400">
<br>
<b>Figure 20.2</b> Part B – Signal observation during Step 8.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/34a0eca9-2324-4b02-885c-e3966ba63c75" width="400">
<br>
<b>Figure 20.3</b> Part B – Signal observation during Step 10.
</p>


---

### Question 3  
**What’s the significance of the signal on the Baseband LPF’s output?**

**Answer:**

The output of the baseband low-pass filter represents the **recovered message signal**. This shows that the undersampling process has successfully converted the high-frequency DSBSC signal into a baseband signal containing the original message information.

---

### Question 4  
**Given the sampling frequency is 8.333 kHz, which harmonic in the sampling signal is demodulating the DSBSC signal?**

**Answer:**

The carrier frequency is **100 kHz** and the sampling frequency is **8.333 kHz**.

Harmonic number:

100 kHz ÷ 8.333 kHz ≈ **12**

Therefore, the **12th harmonic** of the sampling signal is responsible for demodulating the DSBSC signal.

---

# Part C – Synchronisation

In this section, the effect of synchronization errors between the sampling signal and the modulated carrier was investigated.

### Procedure

The sampling signal source was modified by replacing the Master Signals module’s digital output with a signal generated from the **VCO module**. The VCO frequency was adjusted so that its output approximated the original sampling frequency used earlier.

The recovered signal was observed on the oscilloscope while the VCO frequency was slightly adjusted using the frequency control knob. Changes in the recovered message signal were noted as the frequency error increased or decreased.

This demonstrated how synchronization errors between the sampling signal and the modulated carrier can affect demodulation performance.

### Results
<p align="center">
<img src="https://github.com/user-attachments/assets/f45476e6-176b-4f9c-a60f-5a505e4505cf" width="400">
<br>
<b>Figure 20.4</b> Part C – Signal observation during Step 19.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/18942747-2211-44b5-bce2-5e47886e85ce" width="400">
<br>
<b>Figure 20.5</b> Part C – Signal observation during Step 21.
</p>

---

### Question 5  
**Why doesn’t this solve the problem and allow the demodulator to recover the message?**

**Answer:**

Adjusting the VCO frequency manually cannot perfectly match the required sampling frequency and phase of the carrier signal. Even very small frequency or phase differences cause the recovered signal to drift or distort. Because of this mismatch, proper synchronization cannot be maintained, preventing the demodulator from consistently recovering the original message.

---

## Observations

The DSBSC signal produced two sidebands at frequencies slightly above and below the carrier. When undersampling was applied using the sample-and-hold circuit, aliasing caused the high-frequency components of the signal to shift into the baseband region. After passing through the baseband low-pass filter, the original message signal was successfully recovered.

However, when synchronization errors were introduced by using the VCO module, the recovered signal became distorted. This showed that precise synchronization is required for successful demodulation using undersampling.

---

## Conclusion

This experiment demonstrated the concept of undersampling in software defined radio systems. A DSBSC signal was generated and then sampled at a rate much lower than its carrier frequency. Through the process of aliasing, the signal was effectively translated into the baseband region, allowing the original message to be recovered using a low-pass filter.

The experiment also highlighted the importance of synchronization between the sampling signal and the carrier frequency. Small mismatches in frequency or phase can significantly affect the quality of the recovered signal.

Undersampling is an important technique used in modern SDR systems because it allows high-frequency signals to be processed using lower sampling rates, reducing hardware requirements while still preserving the information contained in the signal.

---

## Additional Notes

### Advantages of Undersampling

- Allows high-frequency signals to be processed with lower sampling rates  
- Reduces ADC speed requirements  
- Useful for software defined radio receivers  
- Enables direct down-conversion to baseband  

### Limitations

- Requires careful selection of sampling frequency  
- Sensitive to synchronization errors  
- Aliasing can occur if sampling conditions are not properly chosen  

### Applications

Undersampling is commonly used in:

- Software Defined Radio (SDR)
- RF receivers
- Digital signal processing systems
- Communication signal analysis
