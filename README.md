# Tactical\_FSK\_Modem 🛰️

**Tactical\_FSK\_Modem** is an audio-based wireless visual and text data communication solution designed for high reliability in extreme environments. Integrated with **Forward Error Correction (FEC)**, this system can detect and repair bit corruption in real-time during over-the-air transmission.

## 🛡️ Forward Error Correction (FEC) Aspects

The system utilizes the **Hamming (7,4)** algorithm to maintain data integrity:

  * **Real-time Error Correction**: Every 4 bits of data are wrapped into a 7-bit block code, allowing the receiver (RX) to automatically correct single-bit errors without needing to retransmit data.
  * **Integrity Assurance**: Significantly reduces the Bit Error Rate (BER) in weak signal conditions (Low SNR) or when subjected to radio static interference.
  * **Toggleable Protection**: The FEC feature can be enabled or disabled via the interface to balance between pure transmission speed and data security.

## ✨ Key Features

  - **Auto-Reset & Sync Melody**: Uses a specific "Start Melody" tone sequence (1400Hz - 1000Hz) that commands the receiving unit (RX) to automatically reset its canvas and begin image decoding.
  - **720P Hardened Output**: Forces image transmission at a vertical resolution of 720 pixels to increase resistance against visual noise.
  - **Smart Viewport**: A compact UI preview display (Compact Mode) to save workspace while maintaining sharp HD file output.
  - **Tactical Aesthetics**: An "Amber Monitoring Terminal" themed UI optimized for visibility during field operations.

## 📱 Mobile Portability (Android)

  - **Field-Ready**: Operate directly from a smartphone connected to a Handheld Transceiver (HT) or Rig via an audio interface cable.
  - **Low Latency**: Audio drivers optimized for MFSK tone frequency accuracy on mobile devices.

## 🛠️ Technical Details

| Parameter | Configuration |
|-----------|-------------|
| **Modulation** | MFSK (Multi-Frequency Shift Keying) |
| **Error Correction** | **Hamming (7,4) FEC** |
| **Transmission Resolution** | 720P (Fixed Height for Robustness) |
| **Start Signaling** | 1400Hz -\> 1000Hz -\> 1400Hz (VIS) |
| **Sync Pulse** | 1100Hz & 1300Hz (Line-by-line Sync) |
| **Security** | Registry-Based Auth & DJB2 Hashing |

## 🚀 How to Run

1.  **Windows**: Run `Tactical_FSK_Modem.exe`, select your file, and press `TRANSMIT`.
2.  **Android**: Install the APK, grant Microphone permissions, and connect to your radio device.
3.  **FEC Note**: Ensure the **"Enable FEC (Hamming 7,4)"** option is checked on both sides (TX & RX) for maximum data protection.

-----

**Developer Note**:
This project was independently developed by **YD1RUH** for tactical radio communication education.

© 2026 YD1RUH. **Tactical\_FSK\_Modem** - *Correction in Silence, Clarity in Noise.*
