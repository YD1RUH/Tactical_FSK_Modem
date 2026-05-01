# Tactical_FSK_Modem 🛰️

![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android-green?style=for-the-badge)
![UI-Style](https://img.shields.io/badge/UI-Tactical_Amber-orange?style=for-the-badge)
![FEC](https://img.shields.io/badge/FEC-LDPC%20%7C%20Viterbi%20%7C%20Hamming-blue?style=for-the-badge)

**Tactical_FSK_Modem** is an audio-based wireless visual and text data communication solution designed for high reliability in extreme environments. Equipped with multi-mode **Forward Error Correction (FEC)**, this system is capable of detecting and repairing bit corruption in real-time during over-the-air transmission.

## 📡 Signal Visualization & Modulation
The system now supports multi-tone modulation for improved bandwidth efficiency:

| FSK Modulation (Data) | MFSK (Send Image Like FAX) |
|---------------------------|------------------------------|
| ![FSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/FSK.png) | ![MFSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/MFSK.png) |
| *Standard Frequency Shift Keying* | *Multi-Frequency Shift Keying for 720P Data* |

| Modulation Type | Description |
|-----------------|-------------|
| **2-Tone FSK** | Standard AFSK with adjustable *Space/Mark* frequencies. |
| **8-FSK (New)** | 8-tone modulation (3 bits per symbol) with 11 preset modes (45 - 350 Baud) for high throughput in low SNR conditions. |
| **MFSK Image** | Analog multi-tone modulation (SSTV Style) with hardened 720P vertical resolution. |

## 🛡️ Forward Error Correction (FEC) Aspects
Select error correction algorithms based on noise conditions (SNR):
* **None**: Standard 10-bit frame (Fastest, no protection).
* **Hamming (7,4)**: Corrects isolated single-bit flips (16-bit frame).
* **Reed-Solomon (Simulated)**: Heavy protection using *Triple Modular Redundancy* logic.
* **Convolutional (Viterbi)**: Highly resilient against continuous background noise.
* **LDPC (16,8) Systematic (New)**: *Low-Density Parity-Check* code with an *Iterative Bit-Flipping decoder* (20 iterations) for critical data transmission.

## ✨ Key Features
- **New! Smart Auto-Docking**: The Android UI now automatically organizes windows (Send Text, File, Image, BBS) into a clean tabbed system upon startup.
- **Integrated BBS Server**: Fully functional Bulletin Board System module for automated text broadcasting (`/request_berita`).
  - **Android Path**: `/storage/emulated/0/Documents/Tactical_FSK_Modem/news`.
  - **Desktop Path**: `news` folder in the same directory as the `.exe`.
- **Advanced DSP Audio**: Features **Automatic Gain Control (AGC)** for the receiver and manual TX output gain adjustment to ensure optimal signal levels.
- **JNI Native Android Bridges**: Full integration with the Android system for *File Picker*, *Hide Keyboard*, and exporting intercepted image files.
- **Byte Stuffing Protocol**: Transmission synchronization using *Start/End framing* and *Escape characters* for text data integrity.

## 🛠️ Technical Details
| Parameter | Configuration |
|-----------|-------------|
| **Modulation** | FSK (2-Tone) & 8-FSK (8-Tone) |
| **Baud Rate** | 1 - 1200 bps (FSK) \| Preset 45 - 350 Baud (8-FSK) |
| **Error Correction** | LDPC, Viterbi, Hamming, RS-Sim |
| **Start Signaling** | 1400Hz -> 1000Hz -> 1400Hz (VIS Reset) |
| **BBS Directory** | Documents/Tactical_FSK_Modem/news |

## 🚀 How to Run
1. **Windows**: Run `Tactical_FSK_Modem.exe`.
2. **Android**: Install the APK, grant Microphone & Storage permissions.
3. **Setup**: Go to `Config > Modulation Configuration` to select the mode (FSK/8-FSK) and FEC.
4. **BBS**: Place `.txt` files in the `Documents/Tactical_FSK_Modem/news` folder to enable the news feature.
5. **Transmit**: Enter text or select a file/image, then press `TRANSMIT PACKET`.

---
**Developer Note**: 
This project was independently developed by **YD1RUH** for tactical radio communication education and experimental digital signal processing (DSP).

© 2026 YD1RUH. **Tactical_FSK_Modem**
