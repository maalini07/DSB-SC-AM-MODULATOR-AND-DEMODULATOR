# DSB-SC-AM-MODULATOR-AND-DEMODULATOR
## AIM:
To write a program to perform DSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

## EQUIPMENTS REQUIRED
•	Computer with i3 Processor 
•	SCI LAB

Note: Keep all the switch faults in off position

## ALGORITHM:

1.	Define Parameters:
   
    •	Fs: Sampling frequency.
    
    •	T: Duration of the signal.
    
    •	Fc: Carrier frequency.
    
    •	Fm: Frequency of the message signal.
    
    •	Amplitude: Maximum amplitude of the message signal.

2.	Generate Signals:
 
  •	Message Signal: A sinusoidal signal that will be modulated.
  
  •	Carrier Signal: A high-frequency sinusoidal signal used for modulation.

3.	DSBSC Modulation:
   
  •	Modulated Signal: Multiply the message signal by the carrier signal to produce the DSBSC signal.

4.	DSBSC Demodulation:

  •	Multiplication: Multiply the modulated signal by the carrier signal to get the product of the message signal with itself (i.e., the original message signal plus high-frequency components).

  •	Low-pass Filtering: Apply a Butterworth low-pass filter to remove the high- frequency components and recover the original message signal.

5.	Visualization:
   
  Plot the message signal, carrier signal, DSBSC modulated signal, and the recovered signal after demodulation.

## PROCEDURE

  •	Refer Algorithms and write code for the experiment.
  
  •	Open SCILAB in System
  
  •	Type your code in New Editor
  
  •	Save the file
   
  •	Execute the code
  
  •	If any Error, correct it in code and execute again
  
  •	Verify the generated waveform using Tabulation and Model Waveform
  
## MODEL GRAPH:
<img width="503" height="479" alt="image" src="https://github.com/user-attachments/assets/9f4fdea5-8f1d-44ae-a75a-8c3737088c0a" />

## PROGRAM:
```
Am = 7;
Ac = 14;
fm = 653;
fc = 6530;
fs = 653000;
t = 0:1/fs:2/fm;
m = Am * cos(2 * 3.14 * fm * t);
subplot(4,1,1);
plot(t, m, 'b');
title('Message Signal');
xlabel('Time (s)');
ylabel('Amplitude');
c = Ac * cos(2 * 3.14 * fc * t);
subplot(4,1,2);
plot(t, c, 'r');
title('Carrier Signal');
xlabel('Time (s)');
ylabel('Amplitude');
s = (Ac + m) .* cos(2 * 3.14 * fc * t);
subplot(4,1,3);
plot(t, s, 'k');
title('Modulated Signal');
xlabel('Time (s)');
ylabel('Amplitude');
envelope = abs(hilbert(s)); 
demod = envelope - Ac;
subplot(4,1,4);
plot(t, demod, 'g');
title('Demodulated Signal');
xlabel('Time (s)');
ylabel('Amplitude');

```
## TABULATION:
![a00d4d44-ab30-4804-ba74-fdd0929f5e49](https://github.com/user-attachments/assets/c938e882-4a98-4aef-9001-78925c0ecf21)

## OUTPUT:
<img width="674" height="572" alt="image" src="https://github.com/user-attachments/assets/42d72da4-c1c8-4ddd-b1b0-d02d1c73afd7" />

## RESULT:
Thus the DSB-SC-AM Modulation and Demodulation is generated.
