---
layout: page
permalink: /projects/mic-amplifier/
title: Mic Amplifier
subtitle: A mic amplifier capable of both balanced and unbalanced input signal, noise filtering, 5-band equalizing, and 25.92W max output power
---

---

# Design

### Mic Pre-Amplifier

The designed circuit is a microphone preamp with two channels, compatible of both balanced and unbalanced input signal, and is able to boost the signal level from input MIC signal level of -60 ~ -40 dB to output LINE signal level of -20 ~ 0 dB with an adjustable gain from 20 ~ 40dB.

![Preamp Design](/img/projects/mic-amplifier/preamp-design.png)
<br>
*Figure 1.1. Preamp Design*

- **Input Selection Stage:**<br>
  DPDT switch is applied to switch the input between balanced and unbalanced signal connectors.

- **Noise Cancelling Stage:**<br>
  INA103KP low noise, low distortion instrumentation amplifier is used with its output stage gain adjust mode, to cancel out the noise from the balanced signal and amplifier the signal by 20dB at the same time.

  ![INA103 Gain Adjustment of Output Stage](/img/projects/mic-amplifier/INA103.png)
  <br>
  *Figure 1.2. INA103 Gain Adjustment of Output Stage*

  $$A_{V}=\frac{(R_2 || 12 k\omega)+R_1+R_3}{R_2 || 12 k\omega}$$

  *[12 $$k\omega$$ as internal resistance between 10 and 11]*

  Gain $$A_V$$ set to 10 (20dB) due to design purpose.
  <br>
  $$R_1$$ and $$R_3$$ set to 1.2 $$k\omega$$, $$R_2$$ set to 273 $$\omega$$ to meet main requirement as well as limiting current

- **Band-pass Filtering Stage:**<br>
  Active band-pass filter with cutoff frequency 20Hz and 20kHz, using TL082 operational amplifier, is implemented to filter out the noises with frequency out of human hearing range.

  ![Active Band-pass Filter using TL082 (20Hz to 20kHz)](/img/projects/mic-amplifier/TL082.png)
  <br>
  *Figure 1.3. Active Band-pass Filter using TL082 (20Hz to 20kHz)*

  $$f_{c1}=\frac{1}{2\pi R_1C_1}=\frac{1}{2\pi \times 10 k\omega \times 0.8\mu F}=19.89 Hz$$
  
  $$f_{c2}=\frac{1}{2\pi R_2C_2}=\frac{1}{2\pi \times 100 k\omega \times 80 pF}=19.89 kHz$$

- **Output Adjustment Stage:**<br>
  TL082 operational amplifier is used to invert the signal that is inverted during the band-pass filtering stage to create an output signal in phase with the input signal. A 10k potentiometer is also implemented to enable gain adjust.

  ![Output Adjustment Amplifier using TL082](/img/projects/mic-amplifier/TL082-2.png)
  <br>
  *Figure 1.4. Output Adjustment Amplifier using TL082*

  $$A_V=\frac{R_{10}+R_{11}}{R_9}=\frac{(0\omega \sim 10k\omega)+1.1k\omega}{1.1 k\omega}=1 \sim 10.09=0dB \sim 20.08dB$$


### 5 Band Equalizer

The designed circuit is a 5-band equalizer with 5 set points across human hearing range, 108Hz, 343Hz, 1.08kHz, 3.43kHz, and 10.8kHz. Each set point has gain adjusted by external potentiometer.

KA2223 5-band graphic equalizer amplifier chip is used for the 5-band equalizer application, with resonance frequency controlled by external capacitors and gain control through external adjustable resistors.

![5 Band Equalizer Design](/img/projects/mic-amplifier/equalizer.png)
<br>
*Figure 2.1. 5 Band Equalizer Design*

$$f=\frac{1}{2\pi \sqrt{R_1R_2C_1C_2}}$$

*[$$R_1$$,$$R_2$$ are 1.2 $$k\omega$$ and 68$$k\omega$$ on-chip resistors]*

$$f_1=\frac{1}{2\pi \sqrt{1.2k\omega \times 68 k\omega \times 0.68 \mu F \times 39 nF}}=108.19 Hz$$
<br>
$$f_2=\frac{1}{2\pi \sqrt{1.2k\omega \times 68 k\omega \times 0.22 \mu F \times 12 nF}}=342.90 Hz$$
<br>
$$f_3=\frac{1}{2\pi \sqrt{1.2k\omega \times 68 k\omega \times 68 nF \times 3.9 nF}}=1.08 kHz$$
<br>
$$f_4=\frac{1}{2\pi \sqrt{1.2k\omega \times 68 k\omega \times 22 nF \times 1.2 nF}}=3.43 kHz$$
<br>
$$f_5=\frac{1}{2\pi \sqrt{1.2k\omega \times 68 k\omega \times 6.8 nF \times 390 pF}}=10.82 kHz$$

### Power Amplifier

The designed circuit is a class-AB power amplifier with gain of 31 (28.8 in real test) at 1kHz, highest average output power of 38W (25.92W in real test) across 8Ω load at 1kHz and ±28V supply voltage, and surface temperature maintained at 51.8℃ during highest power output.

![Power Amplifier Schematic](/img/projects/mic-amplifier/power-amp.png)
<br>
*Figure 3.1. Power Amplifier Schematic*

- **Gain Control:**<br>
  $$R_2$$, $$R_3$$, and internal resistor at output pin work together to control the gain of the amplifier.
  
  $$Gain=1+\frac{R_3+R_{in}}{R_2}=1+\frac{20 k\omega + 10 k\omega}{1 k\omega}=31$$

- **Mute Control:**<br>
  LM3886TF chip is designed with muting function that turns off when over 0.5mA is drawn from pin 8. The mute switch is applied to toggle the mute function and the led is used to indicate the status of output.
  
  $$I_{drawn}=\frac{|V_{DD}|-2\times V_{diode}}{R_4}=\frac{|-28 V|-2\times 1.3V}{10 k\omega}=2.54 mA > 0.5 mA$$

---

# Testing

### Mic Pre-Amplifier

- The unbalanced signal input is used for testing, and a sine wave signal with -40dB(10mV) RMS is applied at the input.
- The frequency of the input signal sweeps from 1Hz to 100kHz to obtain the frequency response of the circuit.
- SNR is also calculated through the measurements of noise and signal power.

**Frequency Response**

![Frequency Response](/img/projects/mic-amplifier/freq-response.png)
<br>
*Figure 1.5. Frequency Response Data*

$$\textrm{Ratio Gain}=\frac{\textrm{Output RMS}}{\textrm{Input RMS}}$$

$$\textrm{dB Gain}=20 log_{10} \textrm{Ratio Gain}$$

![Frequency Response with Ratio Gain](/img/projects/mic-amplifier/freq-ratio-gain.png)
<br>
*Figure 1.6. Frequency Response with Ratio Gain*

![Frequency Response with dB Gain](/img/projects/mic-amplifier/freq-db-gain.png)
<br>
*Figure 1.7. Frequency Response with dB Gain*

**SNR:**

$$\textrm{Noise RMS}=14.4 mV_{pp}=5.09 mV_{rms}=-45.86 dBV$$

$$\textrm{Signal RMS}=1V_{rms}=0 dBV$$

$$SNR = 0dBV-(-45.86 dBV)=45.86dB$$

### 5 Band Equalizer

-	A sine wave signal input is used for testing, with an amplitude of 500 $$mV_{rms}$$.
-	The frequency of the input signal sweeps from 1 Hz to 100 kHz to obtain the frequency response of the circuit.
-	THD of the chip is given in datasheet with value of 0.02% at 1 kHz.

**Frequency Response**

![108 Hz Frequency Response](/img/projects/mic-amplifier/108-freq-response.png)
<br>
*Figure 2.2. 108 Hz Frequency Response Data*

![108 Hz Frequency Response in dB](/img/projects/mic-amplifier/108-freq-db.png)
<br>
*Figure 2.3. 108 Hz Set Point Circuit Frequency Response in dB*

![343 Hz Frequency Response](/img/projects/mic-amplifier/343-freq-response.png)
<br>
*Figure 2.4. 343 Hz Frequency Response Data*

![343 Hz Frequency Response in dB](/img/projects/mic-amplifier/343-freq-db.png)
<br>
*Figure 2.5. 343 Hz Set Point Circuit Frequency Response in dB*

![1.08 kHz Frequency Response](/img/projects/mic-amplifier/1.08k-freq-response.png)
<br>
*Figure 2.6. 1.08 kHz Frequency Response Data*

![1.08 kHz Frequency Response in dB](/img/projects/mic-amplifier/1.08k-freq-db.png)
<br>
*Figure 2.7. 1.08 kHz Set Point Circuit Frequency Response in dB*

![3.43 kHz Frequency Response](/img/projects/mic-amplifier/3.43k-freq-response.png)
<br>
*Figure 2.8. 3.43 kHz Frequency Response Data*

![3.43 kHz Frequency Response in dB](/img/projects/mic-amplifier/3.43k-freq-db.png)
<br>
*Figure 2.9. 3.43 kHz Set Point Circuit Frequency Response in dB*

![10.8 kHz Frequency Response](/img/projects/mic-amplifier/10.8k-freq-response.png)
<br>
*Figure 2.10. 10.8 kHz Frequency Response Data*

![10.8 kHz Frequency Response in dB](/img/projects/mic-amplifier/10.8k-freq-db.png)
<br>
*Figure 2.11. 10.8 kHz Set Point Circuit Frequency Response in dB*

![Overall Frequency Response](/img/projects/mic-amplifier/all-freq-response.png)
<br>
*Figure 2.12. Overall Circuit Frequency Response Data*

![Overall Frequency Response in dB](/img/projects/mic-amplifier/all-freq-db.png)
<br>
*Figure 2.13. Overall Circuit Frequency Response in dB*

### Power Amplifier

**Input Signal:**
<br>
The signal is set to sine wave with 500 $$mV_{rms}$$, 1 kHz, 0 V offset applied at the input.

**Output Waveform:**

![Output Waveform](/img/projects/mic-amplifier/waveform.jpg)
<br>
*Figure 3.2. Output Waveform on Oscilloscope*

**Gain:**

$$\textrm{Ratio Gain}=\frac{\textrm{Output RMS}}{\textrm{Input RMS}}=\frac{14.40 V}{500 mV}=\underline{28.8}$$

$$\textrm{dB Gain}=20 log_{10} \textrm{Ratio Gain}=20 log_{10} 28.8=\underline{29.19dB}$$

**Maximum Average Power Output:**

$$P_{average}^{max}=\frac{(V_{rms}^{max})^2}{R_{load}}=\frac{(14.40 V)^2}{8\omega}=\underline{25.92 W}$$

**Heat Dissipation:**

$$\theta_{sa}=\frac{(T_{jmax}-T_{amb})-P_{dmax}(\theta_{jc}+\theta_{cs})}{P_{dmax}}$$

$$\theta_{sa}=\textrm{Maximum thermal resistance of heat sink}$$
<br>
$$T_{jmax}=\textrm{Maximum junction temperature=150℃ (from Datasheet)}$$
<br>
$$T_{amb}=\textrm{Ambient temperature=25℃ (Typical Room Temperature)}$$
<br>
$$P_{dmax}=\textrm{Maximum power dissipation=25.92W (see above)}$$
<br>
$$\theta_{jc}=\textrm{Thermal resistance from junction to case=0.21℃/W (from thermal paste)}$$
<br>
$$\theta_{cs}=\textrm{Thermal resistance from case to heat sink=2℃/W (from Datasheet)}$$

So,
$$\theta_{sa}=\underline{2.6125℃/W}$$

Heat sink used has thermal resistance of 0.80 ℃/W, which is smaller than the maximum value, as required. During test, chip surface temperature maintained at 51.8℃ at 25.92 W output, within maximum operating temperature range (150℃).

### Integrated System

**Input Signal:**
<br>
The signal is set to sine wave with 4 $$mV_{rms}$$, 1 kHz, 0 V offset applied at the input.

**Output Waveform**

![Output Waveform at 1 kHz](/img/projects/mic-amplifier/waveform-1k.jpg)
<br>
*Figure 4.1. Output Waveform on Oscilloscope (at 1 kHz)*

![Output Frequency Response Table](/img/projects/mic-amplifier/freq-response-table.png)
<br>
*Figure 4.2. Frequency Response Data of Output Waveform (20 Hz~20 kHz Filter at Pre-amp)*

![Output Frequency Response Ratio](/img/projects/mic-amplifier/freq-response-ratio.png)
<br>
*Figure 4.3. Frequency Response of Output Waveform (20 Hz~20 kHz Filter at Pre-amp)*

![Output Frequency Response dB](/img/projects/mic-amplifier/freq-response-db.png)
<br>
*Figure 4.4. Frequency Response of Output Waveform in dB (20 Hz~20 kHz Filter at Pre-amp)*

**THD measured at the input to the power stage at 1 kHz = 0.0635%**

**Frequency Response of Filters at Output Stage:**

![Output 108 Hz Filter Frequency Response](/img/projects/mic-amplifier/freq-response-108.png)
<br>
*Figure 4.5. Frequency Response Data (108 Hz Filter)*

![Output 108 Hz Filter Frequency Response in dB](/img/projects/mic-amplifier/freq-db-108.png)
<br>
*Figure 4.6. Frequency Response in dB (108 Hz Filter)*

![Output 343 Hz Filter Frequency Response](/img/projects/mic-amplifier/freq-response-343.png)
<br>
*Figure 4.7. Frequency Response Data (343 Hz Filter)*

![Output 343 Hz Filter Frequency Response in dB](/img/projects/mic-amplifier/freq-db-343.png)
<br>
*Figure 4.8. Frequency Response in dB (343 Hz Filter)*

![Output 1.08 kHz Filter Frequency Response](/img/projects/mic-amplifier/freq-response-1.08k.png)
<br>
*Figure 4.9. Frequency Response Data (1.08 kHz Filter)*

![Output 1.08 kHz Filter Frequency Response in dB](/img/projects/mic-amplifier/freq-db-1.08k.png)
<br>
*Figure 4.10. Frequency Response in dB (1.08 kHz Filter)*

![Output 3.43 kHz Filter Frequency Response](/img/projects/mic-amplifier/freq-response-3.43k.png)
<br>
*Figure 4.11. Frequency Response Data (3.43 kHz Filter)*

![Output 3.43 kHz Filter Frequency Response in dB](/img/projects/mic-amplifier/freq-db-3.43k.png)
<br>
*Figure 4.12. Frequency Response in dB (3.43 kHz Filter)*

![Output 10.8 kHz Filter Frequency Response](/img/projects/mic-amplifier/freq-response-10.8k.png)
<br>
*Figure 4.13. Frequency Response Data (10.8 kHz Filter)*

![Output 10.8 kHz Filter Frequency Response in dB](/img/projects/mic-amplifier/freq-db-10.8k.png)
<br>
*Figure 4.14. Frequency Response in dB (10.8 kHz Filter)*

<hr>

# Conclusion

### Mic Preamplifier
The preamp circuit meets all the design specification and requirements.

The frequency response shows a clear band-pass filter pattern with cutoff frequency close to 20Hz and 20kHz, meeting the design purpose. The power of signal only loses 0.35dB during the band-pass filtering process, which is acceptable.

The SNR calculation shows a result of 45.68 dB, which is significant, but it’s still acceptable considering the prototyping method of breadboard and bridging wires.

### 5 Band Equalizer
The 5-band equalizer circuit meets all the design specification and requirements.

The frequency response shows five results with peak frequency close to the preset values, meeting the design purpose. The frequency response for overall circuit shows a nearly flat pattern in large scale, and has an average gain of -1.61 dB, which is within the range stated in the IC datasheet, -3.8 dB ~ 2.2 dB.

The total harmonic distortion of the chip is only 0.02%, which is pretty low and decent in audio processing.

### Power Amplifier
The power amplifier circuit meets all the design specification and requirements.

The output power reach 25.92 W at maximum, meeting the design purpose of over 20 W. The gain is 28.8 in test, with 7.09% error from the designed gain of 31, which is acceptable.

Temperature dissipation meets all the speculations through calculation, and in real test has a good performance of maintaining 51.8℃ surface temperature, which is significantly good.

### Integrated System
The integrated system meets all the design purpose.

The frequency response at output stage shows a fine result of the 20 Hz~20 kHz band-pass filter at pre-amp stage, which turns out to do a great job on eliminating wireless communication noises out of human hearing range.

The frequency response for the five equalizer filters at output stage shows effective equalizing functions and doesn’t influence the overall signal power excessively.

The total harmonic distortion of the circuit before the power stage is only 0.0635% at 1 kHz input, which is significantly good. Even added the little distortion caused by the single-chip-solution class AB amplifier, the output audio signal is good enough with negligible noise.
