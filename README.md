# Tactical_FSK_Modem 🛰️

![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android-green?style=for-the-badge)
![UI-Style](https://img.shields.io/badge/UI-Tactical_Amber-orange?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-FEC_Hamming_7,4-red?style=for-the-badge)

**Tactical_FSK_Modem** is an audio-based wireless visual and text data communication solution designed for high reliability in extreme environments. Integrated with **Forward Error Correction (FEC)**, this system can detect and repair bit corruption in real-time during over-the-air transmission.

## 📡 Signal Visualization
Below are the visual representations of the modulation techniques used within the system:

| FSK Modulation (Data) | MFSK (Send Image Like FAX) |
|---------------------------|------------------------------|
| ![FSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/FSK.png) | ![MFSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/MFSK.png) |
| *Basic Frequency Shift Keying* | *Multi-Frequency Shift Keying for 720P Data* |

## 🛡️ Forward Error Correction (FEC) Aspects
The system utilizes the **Hamming (7,4)** algorithm to maintain data integrity:
* **Real-time Error Correction**: Every 4 bits of data are wrapped into a 7-bit block code, allowing the receiver (RX) to automatically correct single-bit errors.
* **Integrity Assurance**: Significantly reduces the Bit Error Rate (BER) in weak signal conditions (Low SNR).
* **Toggleable Protection**: Can be enabled or disabled via the interface to balance between speed and security.

## ✨ Key Features
- **Auto-Reset & Sync Melody**: Specific tone sequence (1400Hz - 1000Hz) for automatic RX canvas reset.
- **720P Hardened Output**: Forced 720-pixel vertical resolution for noise resistance.
- **Smart Viewport**: Compact UI preview display while maintaining sharp HD file output.
- **Tactical Aesthetics**: "Amber Monitoring Terminal" themed UI for field operations.
- **Works With HAMLIB**: support RIG device with CAT Controller (Only Desktop App).

## 📱 Mobile Portability (Android)
- **Field-Ready**: Connect your smartphone to a Handheld Transceiver (HT) via an audio interface cable.
- **Low Latency**: Optimized audio drivers for MFSK tone accuracy on mobile devices.

## 🛠️ Technical Details
| Parameter | Configuration |
|-----------|-------------|
| **Modulation** | FSK (Data) & MFSK (FAX Image) |
| **Error Correction** | **Hamming (7,4) FEC** |
| **Transmission Resolution** | 720P (Fixed Height) |
| **Start Signaling** | 1400Hz -> 1000Hz -> 1400Hz (VIS) |
| **Security** | Registry-Based Auth & DJB2 Hashing |

## 🚀 How to Run
1. **Windows**: Run `Tactical_FSK_Modem.exe`, select your file, and press `TRANSMIT`.
2. **Android**: Install the APK, grant Microphone permissions, and connect to your radio.
3. **FEC Note**: Ensure **"Enable FEC (Hamming 7,4)"** is checked on both sides for maximum protection.

## On Progress Feature
1. Adding BBS Server (still in testing)

---
**Developer Note**: 
This project was independently developed by **YD1RUH** for tactical radio communication education.

© 2026 YD1RUH. **Tactical_FSK_Modem**
