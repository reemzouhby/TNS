
# Automatic Audio Signal Filtering Project

## Overview

This project demonstrates the process of filtering an audio signal to remove noise using various techniques. The objective is to take a clean audio signal, introduce white noise, and then apply different filters (FIR and IIR) to recover the original clean signal. This project uses signal processing methods to evaluate the effectiveness of each filtering technique in terms of Signal-to-Noise Ratio (SNR).

## Components Used

- **Libraries**:
  - `NumPy`: Used for numerical operations on the audio data.
  - `Librosa`: Used for audio analysis, such as loading the audio file and plotting in time domain.
  - `SciPy`: Used for signal processing, including filtering methods (FIR, IIR).
  - `Matplotlib`: Used for plotting graphs of the audio signals in both time and frequency domains.
  - `Soundfile`: Used for saving the filtered audio to a new file.

## Steps

### 1. **Loading Clean Audio**
   - Load a clean audio file (`clean_audio.wav`).
   - Convert the audio file to an array of samples using the `librosa.load` function.

### 2. **Adding White Noise**
   - Introduce white noise to the clean audio to simulate a noisy signal.
   - Save the noisy audio file (`noisy_audio.wav`).

### 3. **Frequency Range Analysis**
   - Analyze the frequency range of the clean audio signal to understand the distribution of energy across frequencies.
   - Use the Fast Fourier Transform (FFT) to visualize the frequency content.

### 4. **FIR Filter Implementation**
   - Apply different windowing methods (Rectangular, Triangular, Kaiser, Hamming, etc.) to design Finite Impulse Response (FIR) filters.
   - Use the `scipy.signal.firwin` function to create FIR filters and apply them using `scipy.signal.filtfilt`.
   - For each window method, calculate the Signal-to-Noise Ratio (SNR) and display the results in time and frequency domains.

### 5. **IIR Filter Implementation**
   - Apply Infinite Impulse Response (IIR) filters (e.g., Butterworth, Chebyshev, etc.) using the `scipy.signal.iirfilter` function.
   - Use `scipy.signal.sosfiltfilt` for stable IIR filtering.
   - Calculate and compare the SNR for each IIR filter.

### 6. **Evaluation and Comparison**
   - Evaluate the performance of each filter in terms of SNR.
   - Plot the clean vs filtered signals in both time and frequency domains to visualize the filtering effect.

## Results

The project compares the filtering performance of different methods. The Signal-to-Noise Ratio (SNR) is calculated for each method, with the following observations:

- **FIR Filters**: The triangular window performed the best in terms of SNR.
- **IIR Filters**: The Butterworth filter performed the best for noise removal among the IIR filters tested.

## Future Work

- Explore other filter types (e.g., high-pass, low-pass, band-pass).
- Implement real-time filtering techniques for live audio processing.

## Conclusion

This project demonstrates the application of signal processing techniques to filter noise from audio signals. The performance of each filter was evaluated and compared based on SNR, and the results showed that certain windows and filter types outperform others in noise reduction.

