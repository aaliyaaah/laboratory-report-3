# Experiment 16 – Frequency Shift Keying

## Introduction

Frequency Shift Keying (FSK) is a digital modulation technique in which the frequency of a carrier signal changes according to the digital data being transmitted. Instead of changing the amplitude like in ASK, FSK represents binary data by switching between two different frequencies. One frequency represents logic 1 while the other represents logic 0.

FSK is widely used in communication systems because it is less affected by noise compared to amplitude-based modulation. Since most noise affects signal amplitude, frequency-based transmission can maintain better signal reliability.

In this experiment, an FSK signal was generated using a Voltage Controlled Oscillator (VCO) whose output frequency changes depending on the digital input signal. The generated FSK signal was then demodulated using a filter and an envelope detector. Finally, a comparator circuit was used to restore the recovered signal into a clean digital waveform.

---

## Equipment

- Emona Telecoms-Trainer 101 (plus power pack)  
- Dual channel oscilloscope  
- Oscilloscope leads  
- Assorted patch leads  

---

# Part A – Generating an FSK Signal

In this part of the experiment, the FSK signal was produced by using the Sequence Generator module to create a digital signal. This signal was connected to the input of the Voltage Controlled Oscillator so that the oscillator would switch between two different frequencies depending on the digital input.

### Procedure

The oscilloscope was first configured to properly observe the signals in the system. The trigger source and coupling settings were adjusted so that both the digital signal and the modulated signal could be displayed clearly. The input coupling for both channels was set to DC.

The VCO module was then prepared by adjusting its gain and frequency controls. The gain was set to approximately the middle of its range to allow proper modulation, while the frequency adjustment was set to a moderate value so that the difference between the two output frequencies could be observed easily. The range control of the VCO was placed in the low frequency position.

Next, the Sequence Generator module was configured to produce a simple digital data pattern. This digital signal was used as the control signal for the VCO.

After connecting the modules according to the circuit diagram, the oscilloscope was used to observe both the digital signal and the output of the VCO. It was observed that the oscillator output alternated between two different frequencies depending on the state of the digital input signal. This confirmed that the FSK signal was successfully generated.

---

### Question 1

What’s the name for the VCO output frequency that corresponds with logic-1s in the digital data?

**Answer:**  
The frequency that represents logic-1 is called the **mark frequency**.

---

### Question 2

What’s the name for the VCO output frequency that corresponds with logic-0s in the digital data?

**Answer:**  
The frequency that represents logic-0 is called the **space frequency**.

---

### Question 3

Based on your observations of the FSK signal, which of the two is the higher frequency?

**Answer:**  
The **mark frequency** is the higher frequency while the **space frequency** is the lower frequency.

---

# Part B – Demodulating an FSK Signal Using Filtering and an Envelope Detector

To recover the digital data from the FSK signal, a filtering technique was used. Since the FSK signal contains two different frequencies, a tuneable low-pass filter can be adjusted to isolate one of these frequencies. Once the desired frequency component is selected, an envelope detector can convert the signal into a waveform that resembles the original digital data.

### Procedure

The frequency of the VCO was slightly adjusted to ensure that the two frequencies of the FSK signal were clearly distinguishable. The tuneable low-pass filter module was then configured by setting its gain to maximum and initially setting its cut-off frequency to the highest value.

After modifying the circuit to include the filter module, the cut-off frequency of the filter was slowly adjusted while observing the signal on the oscilloscope. The adjustment continued until one of the frequency components of the FSK signal was significantly reduced, leaving mainly one frequency component.

At this point, the output of the filter appeared as bursts of a sinusoidal waveform corresponding to one of the frequencies in the FSK signal. The signal was then passed through an envelope detector to extract the digital information from the filtered waveform.

---

### Question 4

Which of the FSK signal’s two sinewaves is the filter picking out?

**Answer:**  
The filter isolates the **lower frequency component**, which corresponds to the **space frequency**.

---

### Question 5

What does the filtered FSK signal look like?

**Answer:**  
The filtered signal appears as bursts of a **single sinusoidal waveform** that occur only when the selected frequency is present.

---

# Part C – Restoring the Recovered Data Using a Comparator

The signal obtained after demodulation still contains gradual transitions and distortions. To restore the digital signal, a comparator circuit is used. The comparator converts the varying analog waveform into a digital signal by comparing it to a reference voltage.

### Procedure

The circuit was modified to include the envelope detector output as the input to the comparator module. The oscilloscope was then used to observe both the original digital signal and the recovered signal.

The amplitude of the signal entering the comparator was measured, and the Variable DC module was adjusted to provide a reference voltage approximately halfway between the minimum and maximum levels of the signal. This reference level acted as the switching threshold of the comparator.

By slightly adjusting the reference voltage, the output of the comparator began to closely match the original digital signal. The transitions of the recovered signal became sharper and the waveform resembled a clean digital square wave.

---

### Question 7

How does the comparator turn the slow rising voltages of the recovered digital signal into sharp transitions?

**Answer:**  
The comparator compares the input signal with a reference voltage. When the input signal exceeds the reference level, the output switches quickly to a high state. When it falls below the reference level, the output switches to a low state. This process converts gradual voltage changes into sharp digital transitions.

## Observations

During the experiment, it was observed that the output of the VCO changed frequency depending on the state of the digital input signal. When the digital signal was high, the output waveform had a higher frequency, while a lower frequency was produced when the digital signal was low. This confirmed that the system was generating an FSK signal.

When the tuneable low-pass filter was adjusted, one of the two frequency components of the FSK signal could be isolated. The filtered output appeared as bursts of a sinusoidal waveform that corresponded to one of the frequencies of the original FSK signal.

After passing the filtered signal through the envelope detector, the recovered signal began to resemble the original digital data but still contained slow transitions and slight distortions. When the comparator was added and the reference voltage was properly adjusted, the output became a clean digital waveform with sharp transitions, closely matching the original digital signal.

---

## Conclusion

The experiment successfully demonstrated the generation and demodulation of a Frequency Shift Keying (FSK) signal. The VCO module was able to produce two different frequencies depending on the digital input signal, forming the FSK waveform. By using a tuneable low-pass filter and an envelope detector, the digital information was recovered from the modulated signal. Finally, the comparator was able to restore the recovered waveform into a clean digital signal with sharp transitions. This experiment showed how FSK modulation can be used to transmit digital data and how filtering and detection techniques are used to recover the original information.
