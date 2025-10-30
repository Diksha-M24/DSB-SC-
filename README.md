# DSBSC


EX NO: 2	DSB-SC-AM MODULATOR AND DEMODULATOR

AIM:

To write a program to perform DSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor
•	SCI LAB

Note: Keep all the switch faults in off position

Algorithm:

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
PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="703" height="679" alt="image" src="https://github.com/user-attachments/assets/e7c7c7f8-ccf2-41ac-b1f3-325989941a6f" />

Program
clc;
clear;
close;

//// Given parameters
Am = 9.8;          // Message amplitude
Ac = 19.6;         // Carrier amplitude
Fm = 550;          // Message frequency (Hz)
Fc = 5500;         // Carrier frequency (Hz)
Fs = 55000;        // Sampling frequency (Hz)

//// Time vector
t = 0:1/Fs:0.005;  // 5 ms duration

//// Message signal
m = Am * sin(2 * %pi * Fm * t);

//// Carrier signal
c = Ac * sin(2 * %pi * Fc * t);

//// DSB-SC modulated signal
s = m .* c;        // Multiplication (no carrier term added)

//// Plotting all signals
subplot(3,1,1)
plot(t, m)
title('Message Signal')
xlabel('Time (s)')
ylabel('Amplitude (V)')
xgrid()

subplot(3,1,2)
plot(t, c)
title('Carrier Signal')
xlabel('Time (s)')
ylabel('Amplitude (V)')
xgrid()

subplot(3,1,3)
plot(t, s)
title('DSB-SC Modulated Signal')
xlabel('Time (s)')
ylabel('Amplitude (V)')
xgrid()

//// Display tabulation of sample values
disp("   Time(s)        Message(V)        Carrier(V)        DSB-SC(V)");
for i = 1:10:length(t) // every 10th sample for readability
    mprintf("%10.6f    %10.4f    %10.4f    %10.4f\n", t(i), m(i), c(i), s(i));
end

Output Graph
<img width="757" height="719" alt="Screenshot 2025-10-30 090950" src="https://github.com/user-attachments/assets/26c345bb-0221-4c22-a288-0310920ddfff" />




Tablular Column
<img width="783" height="1280" alt="image" src="https://github.com/user-attachments/assets/ed2e5fd7-2215-4e0e-90bd-32bed2ae59fb" />


Result

Thus the DSB-SC-AM Modulation and Demodulation is generated.

