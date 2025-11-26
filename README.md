# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.

 ___Algorithm__:
   
1.Set values for power, gain, frequency, speed of light, and other constants.

2.Calculate wavelength = speed of light ÷ frequency. 

3.Create a list of distances (range).

4.For each distance:

5.Calculate received power using the radar formula.

6.Convert received power to dBm.

__Program__:

```
clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
```
__Calculation:__


![WhatsApp Image 2025-11-26 at 20 45 23_2615a8ea](https://github.com/user-attachments/assets/4f589906-c1ce-4fed-bad6-29f804ef02be)


__Output__:
   
<img width="752" height="693" alt="image" src="https://github.com/user-attachments/assets/196d2a3b-0e42-4e6c-a55a-9306e922fda0" />

<img width="735" height="683" alt="image" src="https://github.com/user-attachments/assets/2ddc4b0c-a3b1-4d8d-9ffc-f3fa3afca552" />

<img width="733" height="687" alt="image" src="https://github.com/user-attachments/assets/da92dec1-45bb-47df-873d-06a87cf480c9" />







__Result__:
   
Thus, the maximum range of a radar system using the Radar Range Equation is verified.



