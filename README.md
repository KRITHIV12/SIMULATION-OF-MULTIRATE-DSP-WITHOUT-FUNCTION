# EXP 6 : SPEECH RECOGNITION USING SCILAB

## AIM: 

To perform and verify multirate DSP without function using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM : 
```clc;
clear;
close;
N = 100;
fs = 50;
t = (0:N-1)/fs;
f0 = 5;

x = sin(2 * %pi * f0 * t);

M = 3;

y_down = x(1:M:$);

L = 2;


x_upsampled = zeros(1, L * length(y_down));
x_upsampled(1:L:$) = y_down;


h = ones(1, 5) / 5;

y_filtered = conv(x_upsampled, h);

clf;
subplot(311); plot(t, x); title("Original Signal");
subplot(312); plot(t(1:M:$), y_down); title("Downsampled Signal");
subplot(313); plot(1:length(y_filtered), y_filtered); title("Filtered Upsampled Signal");
```
## OUTPUT: 
<img width="1908" height="1133" alt="Screenshot 2025-11-10 023054" src="https://github.com/user-attachments/assets/2d8e18c8-0875-44f7-86ff-c9ed8bbbe63d" />

## RESULT: 
Thus the decimation process by a factor M and interpolation process by a factor L using 
SCILAB was implemented. 
