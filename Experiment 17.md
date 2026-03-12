# Experiment 17 – Binary Phase Shift Keying (BPSK)

## Introduction

Binary Phase Shift Keying (BPSK) is a digital modulation technique where the phase of a carrier signal changes depending on the binary data being transmitted. Instead of modifying the amplitude or frequency, the carrier signal shifts its phase by 180° whenever the digital input changes state. This allows digital information to be transmitted reliably through a communication channel.

In this experiment, the process of generating and demodulating a BPSK signal was explored. The signal was produced using a multiplier module that combines a digital data stream with a carrier signal. The transmitted signal was then demodulated using a product detector, and the recovered digital signal was restored using a comparator circuit.

This experiment was conducted using the **TIMS online simulator**, which replicates the modules of the Emona Telecoms-Trainer system in a virtual environment.

---

## Objectives

- To generate a Binary Phase Shift Keying (BPSK) signal.
- To observe how phase changes correspond to digital data transitions.
- To demodulate the BPSK signal using a product detector.
- To recover the transmitted digital signal from the modulated waveform.
- To restore the recovered signal using a comparator.

---

# Procedure

## Part A – Generating a BPSK Signal

The simulation was first configured using the TIMS online simulator. A sequence generator module was used to produce the digital data stream that served as the input signal. This digital signal was connected to the multiplier module together with a carrier signal from the master signals module.

The multiplier module generated the BPSK waveform by combining the digital signal with the carrier. When the digital signal changed state, the phase of the carrier reversed by 180 degrees. The oscilloscope in the simulator was used to observe both the digital signal and the generated BPSK waveform to verify the phase transitions.

---

## Part B – Demodulating a BPSK Signal Using a Product Detector

To recover the transmitted data, a product detector configuration was used. The received BPSK signal was multiplied with a locally generated carrier signal that had the same frequency as the original carrier.

After the multiplication process, the output signal contained both low-frequency and high-frequency components. A tuneable low-pass filter was then used to remove the unwanted high-frequency components, leaving a signal that resembled the original digital data.

The recovered signal was displayed on the oscilloscope and compared with the original digital signal produced by the sequence generator.

---

## Part C – Restoring the Recovered Data Using a Comparator

Although the recovered signal resembled the original digital waveform, it still contained slow transitions due to filtering effects. To correct this, a comparator module was used to clean up the signal.

The output of the low-pass filter was connected to the comparator input. A variable DC reference voltage was then adjusted to set the comparator’s threshold level. When the input signal exceeded the threshold, the comparator produced a high output, and when it fell below the threshold, the output switched to a low level.

By adjusting the threshold voltage appropriately, the recovered waveform was restored into a clear digital signal with sharp transitions.

---

## Questions

### Question 1
**What happens to the BPSK signal on the data stream’s logic transitions?**

When the digital signal changes from 0 to 1 or from 1 to 0, the phase of the carrier signal reverses by 180°. The amplitude and frequency remain the same, but the waveform flips direction at each logic transition.


### Question 2
**What feature of the BPSK signal suggests that it’s a DSBSC signal?**

The BPSK waveform has a constant amplitude and does not contain the original carrier component in its envelope. The signal also shows phase reversals that correspond to the digital data, which is a characteristic of double-sideband suppressed carrier (DSBSC) modulation.


### Question 3
**Why is the recovered digital signal not a perfect copy of the original?**

The recovered signal is not perfect because the demodulation process and filtering introduce distortion and delay. Noise in the channel and limitations of the filter also affect the signal, causing the recovered waveform to have smoother transitions instead of sharp digital edges.


### Question 4
**What can be used to “clean-up” the recovered digital signal?**

A comparator circuit can be used to clean up the recovered signal. It compares the input signal with a reference voltage and converts it into a clear digital waveform with sharp transitions.


### Question 5
**Why does varying the DC voltage on the comparator’s input change the shape of the digital signal?**

Changing the DC voltage adjusts the comparator’s threshold level. If the threshold is set too high or too low, the comparator switches at different points of the waveform, which changes the timing and shape of the output digital signal.

---

## Observations

During the experiment, it was observed that the BPSK signal maintained a constant amplitude while the phase of the carrier changed whenever the digital signal transitioned between logic states. These phase reversals were clearly visible on the oscilloscope when compared with the original digital signal.

After demodulation using the product detector and low-pass filter, the recovered signal resembled the original data but had smoother transitions. Once the comparator was applied, the waveform became a clean digital signal with distinct high and low levels.

When noise was introduced into the simulated communication channel, the recovered signal showed visible distortions. Increasing the noise level made the demodulated signal less accurate, demonstrating how noise affects digital communication systems.

---

## Conclusion

The experiment successfully demonstrated the generation and demodulation of a Binary Phase Shift Keying (BPSK) signal. The BPSK waveform was produced by combining a digital signal with a carrier signal using a multiplier module. The demodulation process used a product detector and a low-pass filter to recover the transmitted information.

Although the recovered signal initially contained distortions, the comparator module was able to restore the waveform into a clean digital signal. This experiment highlighted how phase modulation can be used to transmit digital data and how signal processing techniques are applied to recover information at the receiver. The use of the **TIMS online simulator** allowed the behavior of the communication system to be observed clearly in a virtual environment.

---

## Additional Notes

### Advantages of BPSK

- More resistant to noise compared to amplitude-based modulation methods  
- Provides reliable data transmission since information is carried through phase changes  
- Simple modulation technique compared to more complex phase modulation schemes  

### Disadvantages of BPSK

- Transmits only one bit per symbol, which limits data transmission efficiency  
- Requires accurate phase synchronization between transmitter and receiver  
- Demodulation circuits can be more complex compared to ASK systems  

### Applications

BPSK is commonly used in several communication systems such as:

- Satellite communication systems  
- Wireless communication networks  
- Deep-space communication systems  
- GPS signal transmission
