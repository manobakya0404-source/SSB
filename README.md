# SSB

EXP NO: 3	SSB-SC-AM MODULATION using SCILAB

AIM:

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position


Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: The baseband signal that will be modulated.
•	Carrier Signal: A high-frequency signal used for modulation.
•	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.
3.	SSBSC Modulation:
•	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.
4.	SSBSC Demodulation:
•	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
•	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.
5.	Visualization:
•	Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.


PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="704" height="178" alt="image" src="https://github.com/user-attachments/assets/32ee29b3-0d95-4192-9762-972d50c05c90" />
<img width="706" height="167" alt="image" src="https://github.com/user-attachments/assets/bff0d8fd-d679-444e-af37-0b34585853c1" />

Program
```
am=5.1;
fm=379;
ac=10.2;
fc=3790;
fs=37900;
t=0:1/fs:3/fm;
em1=am*cos(2*3.14*fm*t);
ec1=ac*cos(2*3.14*fc*t);
em2=am*sin(2*3.14*fm*t);
ec2=ac*sin(2*3.14*fc*t);
em=am*cos(2*3.14*fm*t);
subplot(4,1,1);
plot(t,em);
ec=ac*cos(2*3.14*fc*t);
subplot(4,1,2);
plot(t,ec);
eam1=ac*(1+(em1/ac)).*cos(2*3.14*fc*t);
eam2=ac*(1-(em1/ac)).*cos(2*3.14*fc*t);
edsbsc1=eam1-eam2;
eam3=ac*(1+(em2/ac)).*sin(2*3.14*fc*t);
eam4=ac*(1-(em2/ac)).*sin(2*3.14*fc*t);
edsbsc2=eam3-eam4;

elsb=edsbsc1+edsbsc2;
subplot(4,1,3);
plot(t,elsb);

eusb=edsbsc1-edsbsc2;
subplot(4,1,4);
plot(t,eusb);
```
OUTPUT WAVEFORM

TABULATION
<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/8e81542f-c27d-4021-a10b-cf83416f0dfe" />









RESULT:

Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.





