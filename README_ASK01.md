EX -01 SIMULATION OF AMPLITUDE SHIFT KEYING 
AIM :
  To implement ASK.FSK,BPSK using MATLAB.
software requried :
   MATLAB

PROGRAM:
% Amplitude Shift Keying (ASK) Simulation in MATLAB

% Parameters
fs = 1000; % Sampling frequency
bit_rate = 1; % Bits per second
T = 1 / bit_rate; % Bit duration
t = linspace(0, T, fs); % Time vector for one bit
f_carrier = 10; % Carrier frequency

% Generate a random binary signal
bits = randi([0, 1], 1, 10); % 10-bit random sequence
signal = repelem(bits, fs);
time = linspace(0, length(bits) * T, length(signal));

% Carrier wave
carrier = sin(2 * pi * f_carrier * repmat(t, 1, length(bits)));

% ASK Modulation
ask_signal = carrier .* signal;

% Plot signals
figure;

subplot(3,1,1);
plot(time, signal, 'b', 'LineWidth', 2);
title('Binary Signal');
xlabel('Time [s]');
ylabel('Amplitude');
grid on;

subplot(3,1,2);
plot(time, carrier, 'r');
title('Carrier Signal');
xlabel('Time [s]');
ylabel('Amplitude');
grid on;

subplot(3,1,3);
plot(time, ask_signal, 'g');
title('ASK Modulated Signal');
xlabel('Time [s]');
ylabel('Amplitude');
grid on;

OUTPUT:

