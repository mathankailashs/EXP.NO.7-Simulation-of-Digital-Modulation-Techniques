# EXP.NO.7-Simulation-of-Digital-Modulation-Techniques
7. Simulation of Digital Modulation Techniques Such as
   i) Amplitude Shift Keying (ASK)
   ii) Frequency Shift Keying (FSK)
   iii) Phase Shift Keying (PSK)

# AIM
To study the Python simulation for digital modulation techniques.

# SOFTWARE REQUIRED
python using colab.

# ALGORITHMS
Digital Modulation Function: The function digital_modulation takes in binary data, modulation type, carrier frequency, sampling rate, and symbol rate.
Modulation Types: The function supports ASK (Amplitude Shift Keying), FSK (Frequency Shift Keying), and PSK (Phase Shift Keying) modulation types.
Modulated Signal Generation: The function generates the modulated signal based on the chosen modulation type and returns the modulated signal and time vector.
Error Handling: The code includes a try-except block to catch the ValueError that occurs when an incorrect modulation type is passed to the function.
Alternative Data Generation: The code demonstrates how to generate random binary data using numpy.random.randint() for testing with different data patterns

# PROGRAM

i)Amplitude Shift Keying (ASK):

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc = 10 # Carrier frequency in Hz

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Number of samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)

ask_signal = amplitude * message_signal * np.sin(2 * np.pi * fc * t)

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, carrier_signal, 'r')

plt.title('Carrier Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 3)

plt.plot(t, ask_signal, 'g')

plt.title('Amplitude Shift Keying Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

ii)Frequency Shift Keying (FSK):

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc1 = 10 # Frequency for binary '1'

fc2 = 5 # Frequency for binary '0'

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

fsk_signal = amplitude * (np.sin(2 * np.pi * fc1 * t) * message_signal + np.sin(2 * np.pi * fc2 * t) * (1 - message_signal))

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, amplitude * np.sin(2 * np.pi * fc1 * t), 'r', alpha=0.5, label="Carrier for 1")

plt.plot(t, amplitude * np.sin(2 * np.pi * fc2 * t), 'm', alpha=0.5, label="Carrier for 0")

plt.title('Carrier Signals (FSK)')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.legend()

plt.subplot(3, 1, 3)

plt.plot(t, fsk_signal, 'g')

plt.title('Frequency Shift Keying (FSK) Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

iii)Phase Shift Keying (PSK):

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc = 10 # Carrier frequency in Hz

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)

psk_signal = amplitude * np.sin(2 * np.pi * fc * t + np.pi * (1 - message_signal))

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, carrier_signal, 'r')

plt.title('Carrier Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 3)

plt.plot(t, psk_signal, 'g')

plt.title('Phase Shift Keying (PSK) Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

# OUTPUT
ASK:
![ASK](https://github.com/user-attachments/assets/55b0b670-5ae0-484e-80cd-43c33f514054)

FSK:
![FSK](https://github.com/user-attachments/assets/fc6deb55-5f5a-41a6-a5c8-e66dec022d82)

PSK:
![psk](https://github.com/user-attachments/assets/bc88c85d-5a91-44db-87d3-5d68b547e6b3)
 
# RESULT / CONCLUSIONS
Thus the ASK, FSK AND PSK Modulation and Demodulation techniques were analyzed using Python. 
