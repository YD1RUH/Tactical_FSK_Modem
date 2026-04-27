# Tactical_FSK_Modem 🛰️

![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android-green?style=for-the-badge)
![UI-Style](https://img.shields.io/badge/UI-Tactical_Amber-orange?style=for-the-badge)
![FEC](https://img.shields.io/badge/FEC-Viterbi%20%7C%20Hamming%20%7C%20RS-blue?style=for-the-badge)

**Tactical_FSK_Modem** is an audio-based wireless visual and text data communication solution designed for high reliability in extreme environments. Integrated with multi-mode **Forward Error Correction (FEC)**, this system can detect, mitigate, and repair bit corruption in real-time during over-the-air transmission.

## 📡 Signal Visualization
Below are the visual representations of the modulation techniques used within the system:

| FSK Modulation (Data) | MFSK (Send Image Like FAX) |
|---------------------------|------------------------------|
| ![FSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/FSK.png) | ![MFSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/MFSK.png) |
| *Basic Frequency Shift Keying* | *Multi-Frequency Shift Keying for 720P Data* |

## 🛡️ Forward Error Correction (FEC) Aspects
The system offers selectable error correction algorithms to balance transmission speed and data integrity depending on the Signal-to-Noise Ratio (SNR):
* **None**: Standard 10-bit frame (Fastest, no protection).
* **Hamming (7,4)**: 16-bit frame. Wraps every 4 bits into a 7-bit block to correct isolated single-bit flips.
* **Reed-Solomon (Simulated)**: 26-bit frame. Heavy protection using Triple Modular Redundancy logic for severely degraded signals.
* **Convolutional (Viterbi)**: 18-bit frame (Rate 1/2, K=3). Highly resilient "soft-decision" decoding against continuous background noise.

## ✨ Key Features
- **Integrated BBS Server**: Fully functional Bulletin Board System module for automated text broadcasting (`/request_berita`) and responding to remote commands over the radio.
  - **Desktop (Windows)**: Create a folder named `news` in the same directory as the `.exe` file and put your `.txt` files inside it.
  - **Android**: Place your `.txt` files inside the `news` folder within the app's external data directory (usually located at `/storage/emulated/0/Documents/Tactical_FSK_Modem/news`).
- **Advanced DSP Audio Controls**: Features **Automatic Gain Control (AGC)** for the receiver to normalize varying signal envelopes, alongside manual TX output gain adjustments.
- **Hardware PTT (HAMLIB)**: Seamless CAT Controller integration (`rigctl`) for direct hardware PTT automation (Desktop App only).
- **Auto-Reset & Sync Melody**: Specific tone sequences (1400Hz -> 1000Hz) for automatic RX canvas resets during MFSK image transmission.
- **720P Hardened Output**: Forced 720-pixel vertical resolution for noise resistance and structured image reconstruction.
- **Smart Viewport**: Compact UI preview display while maintaining sharp HD file output.
- **Tactical Aesthetics**: "Amber Monitoring Terminal" themed UI tailored for field operations.

## 📱 Mobile Portability (Android)
- **Field-Ready**: Connect your smartphone to a Handheld Transceiver (HT) via an audio interface cable.
- **Low Latency**: Optimized audio drivers for MFSK tone accuracy on mobile devices.

## 🛠️ Technical Details
| Parameter | Configuration |
|-----------|-------------|
| **Modulation** | FSK (Text/Data) & MFSK (FAX Image) |
| **Baud Rate** | Adjustable (1 - 1200 bps) with Auto-Link Mark (+600Hz) |
| **Error Correction** | Selectable (None, Hamming, RS, Viterbi) |
| **Transmission Resolution** | 720P (Fixed Height) |
| **Start Signaling** | 1400Hz -> 1000Hz -> 1400Hz (VIS) |

## 🚀 How to Run
1. **Windows**: Run `Tactical_FSK_Modem.exe`.
2. **Setup**: Go to `Config > Modulation Configuration` to set your desired Baud Rate and select the optimal **FEC Mode**.
3. **Hardware PTT**: (Optional) Go to `Config > Hamlib Configuration` to link your CAT-enabled radio.
4. **Check RIG ID for Hamlib**: [Click This to show table](https://github.com/YD1RUH/Tactical_FSK_Modem/blob/main/RIG_table.md)
5. **Transmit**: Input your text, select a file, or pick an image, then press `TRANSMIT`.
6. **Android**: Install the APK, grant Microphone permissions, and connect to your radio via an audio link cable.

---
**Developer Note**: 
This project was independently developed by **YD1RUH** for tactical radio communication education and experimental digital signal processing.

© 2026 YD1RUH. **Tactical_FSK_Modem**
