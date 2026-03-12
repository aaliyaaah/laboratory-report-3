# Experiment 19 – DSSS Modulation and Demodulation

## Introduction

Direct Sequence Spread Spectrum (DSSS) is a digital communication technique where the message signal is multiplied by a pseudo-noise (PN) sequence before transmission. This spreads the signal energy over a much wider bandwidth, making the signal more resistant to interference and more difficult to intercept.

Unlike conventional modulation techniques, DSSS distributes the signal energy across many small frequency components. Because of this, the transmitted signal can appear similar to noise. However, if the receiver uses the correct PN sequence, the original message can still be recovered.

In this experiment, DSSS modulation and demodulation were explored using the **TIMS Online Simulator**. A DSSS signal was first generated using a simple sinusoidal message. The signal was then observed using the oscilloscope. Afterwards, speech was used as the message signal to observe how DSSS behaves with real signals. A **product detector and low-pass filter** were then used to recover the message. Finally, deliberate interference or jamming was introduced to demonstrate the resistance of DSSS systems to noise and interference.

---

## Objectives

- To understand the principle of Direct Sequence Spread Spectrum (DSSS).
- To generate a DSSS signal using a PN sequence.
- To observe DSSS signals using a simple sinusoidal message and speech.
- To recover the original message using a product detector.
- To examine the effect of interference and jamming on DSSS communication.

---

## Theory

Direct Sequence Spread Spectrum works by multiplying a message signal with a high-rate pseudo-noise (PN) sequence. This operation spreads the signal across a wider frequency range. Although the transmitted signal appears noise-like, the original message can be recovered at the receiver using the same PN sequence.

The spreading process distributes the signal energy across many frequency components. As a result, interference affecting a small portion of the spectrum has minimal impact on the recovered signal. This makes DSSS systems highly resistant to noise, interference, and jamming.

To recover the original message, the received DSSS signal is multiplied by the same PN sequence used during transmission. This process is called **despreading**. After multiplication, a **low-pass filter** removes high-frequency components and restores the original message signal.

---

# Part A – Generating a DSSS Signal Using a Simple Message

In this part of the experiment, a DSSS signal was generated using a simple sinusoidal message. The message signal from the Master Signals module was multiplied with a PN sequence produced by the Sequence Generator. The resulting signal is a spread spectrum signal whose bandwidth is much wider than the original message.

### Procedure

Using the **TIMS Online Simulator**, the communication system modules were connected according to the DSSS modulator configuration. The Master Signals module generated a **2 kHz sinewave message**, while the Sequence Generator produced the **PN sequence** driven by a clock signal. These two signals were applied to the Multiplier module to produce the DSSS signal. The oscilloscope was configured to display both the original message signal and the DSSS signal so their characteristics could be compared.

The timebase and vertical scaling of the oscilloscope were adjusted so that both signals could be clearly observed. The message signal appeared as a clean sinusoidal waveform, while the DSSS signal appeared more complex due to the spreading effect caused by the PN sequence.

### Result
<p align="center">
<img src="https://github.com/user-attachments/assets/7d27a732-dbc3-4458-9145-5da846a9ff55" width="400">
<br>
<b>Figure 19.1</b> Part A – DSSS signal generated using a simple message.
</p>

---

### Question 1  
**What feature of the Multiplier module’s output suggests that it's basically a DSBSC signal?**

**Answer:**  
The output waveform shows that the carrier itself is not directly visible and only the modulated components remain. This indicates that the carrier is suppressed and the signal consists mainly of sideband components, which is characteristic of a **Double Sideband Suppressed Carrier (DSBSC)** signal.

---

### Question 2  
**Why is the DSSS signal so large when it's supposed to be small and indistinguishable from noise?**

**Answer:**  
The DSSS signal appears large in the experiment because the laboratory setup uses amplified signals so they can be clearly observed on the oscilloscope. In real communication systems, the spread signal energy is distributed across many frequency components, which makes it appear small and noise-like.

---

# Part B – Generating a DSSS Signal Using Speech

In this part of the experiment, the sinusoidal message was replaced with a speech signal. This allowed observation of how DSSS behaves when transmitting real-world signals such as voice.

### Procedure

Within the **TIMS Online Simulator**, the connection from the Master Signals module was removed and replaced with the **Speech module output**. The speech signal was then used as the input message for the DSSS modulator. While speaking, humming, or producing sounds into the speech module, the oscilloscope displayed the resulting DSSS waveform.

The timebase was adjusted so the variations in the speech signal could be observed. The DSSS waveform appeared more irregular compared to the sinusoidal message, reflecting the natural variations of speech.

---

### Question 3  
**Why isn't there any signal out of the DSSS modulator when you're not talking?**

**Answer:**  
When no speech is present, the speech module produces little or no signal. Since DSSS modulation multiplies the message signal with the PN sequence, the absence of a message results in little or no output from the modulator.

---

# Part C – Using the Product Detector to Recover the Message

In this part, the DSSS signal was demodulated using a **product detector** and a **tuneable low-pass filter**. The correct PN sequence was used as the local carrier to despread the signal.

### Procedure

The receiver configuration was implemented using the TIMS Online Simulator. The DSSS signal was applied to another Multiplier module along with the same PN sequence used during modulation. This process despread the signal. The output was then passed through a tuneable low-pass filter to remove high-frequency components and recover the original message.

The filter’s gain and cutoff frequency were adjusted until the recovered waveform resembled the original message signal observed earlier.

### Results
<p align="center">
<img src="https://github.com/user-attachments/assets/9a3cf2bd-3c7c-42de-8973-21e4684fff6f" width="400">
<br>
<b>Figure 19.2</b> Part C – Signal observation during Step 18 of the demodulation process.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/92105104-32ca-4082-a193-a67dd7430efd" width="400">
<br>
<b>Figure 19.3</b> Part C – Signal observation during Step 19.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/c9db2a15-8e5f-4c5e-87ad-49c5a656246a" width="400">
<br>
<b>Figure 19.4</b> Part C – Signal observation during Step 21.
</p>

---

### Question 4  
**What does the signal out of the low-pass filter look like?**

**Answer:**  
The signal resembles the original message waveform. If a sinewave message was used, the output appears as a clean sinusoidal signal. When speech is used, the output follows the variations of the speech signal.

---

### Question 5  
**Why does using the wrong PN sequence for the local carrier cause the product detector’s output to look like this?**

**Answer:**  
If the wrong PN sequence is used, the spreading process cannot be properly reversed. Instead of cancelling the spreading effect, the multiplication produces a random waveform that appears as noise. This prevents the original message from being recovered.

---

# Part D – DSSS and Deliberate Interference (Jamming)

This part of the experiment demonstrates how DSSS signals behave in the presence of interference. A jamming signal was introduced into the communication channel using a VCO and an adder module.

### Procedure

Using the TIMS Online Simulator, a **jamming signal** generated by the VCO module was added to the transmitted DSSS signal through the Adder module. The amplitude of the interference was gradually increased while observing both the DSSS signal and the recovered message on the oscilloscope.

The frequency of the jamming signal was varied to observe its effect on the communication system. Later, a broadband interference signal was introduced using the Noise Generator module. Even when the interference level was increased, the recovered message remained relatively clear compared to the distorted transmitted signal.

### Results
<p align="center">
<img src="https://github.com/user-attachments/assets/c0a79374-a2f5-4843-9052-19e3df7402b9" width="400">
<br>
<b>Figure 19.5</b> Part D – Signal observation during Step 30 (case 1).
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/8e6b57ca-0642-44b5-aa86-de9f87dbf040" width="400">
<br>
<b>Figure 19.6</b> Part D – Signal observation during Step 30 (case 2).
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/9b610242-4b80-4413-9290-56d41e5559e6" width="400">
<br>
<b>Figure 19.7</b> Part D – Signal observation at minimum frequency setting (Step 31).
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/c38d3b50-03e0-4408-bc01-f16409544be5" width="400">
<br>
<b>Figure 19.8</b> Part D – Signal observation at maximum frequency setting (Step 31).
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/35708826-8c27-4f9f-a95e-03c40897aab0" width="400">
<br>
<b>Figure 19.9</b> Part D – Signal observation during Step 42.
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/36cabf7d-20eb-4b5b-9fb0-14b1b453c193" width="400">
<br>
<b>Figure 19.10</b> Part D – Final signal output observed during Step 44.
</p>

---

### Question 6  
**Why doesn't the jamming signal interfere with the recovery of the message?**

**Answer:**  
The DSSS system spreads the signal energy across a wide bandwidth. During demodulation, the receiver multiplies the signal with the correct PN sequence, which despreads the desired signal while spreading the interference. As a result, most of the jamming signal energy is removed by the low-pass filter, allowing the original message to be recovered.

---

## Observations

The DSSS signal appeared much more complex than the original message signal due to the spreading effect of the PN sequence. When the correct PN sequence was used in the receiver, the original message was successfully recovered. When the wrong PN sequence was used, the output resembled noise and the message could not be recovered. When interference was introduced, the transmitted DSSS signal became distorted but the recovered message was still recognizable, demonstrating the robustness of spread spectrum communication.

---

## Conclusion

This experiment demonstrated the principles of Direct Sequence Spread Spectrum communication. A DSSS signal was generated by multiplying a message signal with a pseudo-noise sequence. The signal appeared noise-like due to the spreading process. By using the same PN sequence at the receiver, the signal was successfully despread and the original message was recovered.

The experiment also showed that DSSS systems are highly resistant to interference and jamming. Even when strong noise was introduced into the channel, the recovered message remained relatively unaffected. This highlights the advantages of DSSS in modern communication systems.

---

## Additional Notes

### Advantages of DSSS

- High resistance to noise and interference  
- Increased security and privacy  
- Multiple users can share the same bandwidth  
- Reliable communication in noisy environments  

### Disadvantages of DSSS

- Requires synchronization of PN sequences  
- More complex receiver design  
- Requires wider bandwidth than conventional systems  

### Applications

DSSS is used in:

- GPS systems  
- CDMA mobile communication  
- Wi-Fi (802.11 spread spectrum systems)  
- Military communication systems
