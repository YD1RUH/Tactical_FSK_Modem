<a href="https://info.flagcounter.com/DroY"><img src="https://s01.flagcounter.com/count2/DroY/bg_FFFFFF/txt_000000/border_CCCCCC/columns_8/maxflags_20/viewers_0/labels_0/pageviews_0/flags_0/percent_0/" alt="Flag Counter" border="0"></a>

# Tactical_FSK_Modem 🛰️

![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android-green?style=for-the-badge)
![UI-Style](https://img.shields.io/badge/UI-Tactical_Amber-orange?style=for-the-badge)
![FEC](https://img.shields.io/badge/FEC-LDPC%20%7C%20Viterbi%20%7C%20Hamming-blue?style=for-the-badge)
![AGWPE](https://img.shields.io/badge/AGWPE-TNC%20Server-purple?style=for-the-badge)

**Tactical_FSK_Modem** is an audio-based wireless communication system designed for high reliability in extreme RF environments. It supports multi-mode text, file, and image transmission over any radio transceiver with an audio interface, with full Forward Error Correction (FEC), real-time signal visualization, and APRS/TNC integration via AGWPE protocol.

---

## 📡 Signal Visualization & Modulation

| FSK Modulation (Data) | MFSK (Send Image Like FAX) |
|---|---|
| ![FSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/FSK.png) | ![MFSK](https://raw.githubusercontent.com/YD1RUH/Tactical_FSK_Modem/main/MFSK.png) |
| *Standard Frequency Shift Keying* | *Multi-Frequency Shift Keying for 720P image data* |

### Modulation Modes

| Mode | Description | Bits/Symbol | Baud Range |
|---|---|---|---|
| **2-Tone FSK** | Classic AFSK with adjustable Space/Mark frequencies and clock-bit sync | 1 | 1 – 1200 bps |
| **8-FSK** | 8-tone modulation — 12 presets including FT8-style ultra-narrow mode | 3 | 6 – 350 baud |
| **16-FSK** | 16-tone modulation — 6 presets including MFSK16-style narrow mode | 4 | 16 – 125 baud |
| **MFSK Image** | Analog multi-tone SSTV-style transmission, hardened 720P vertical resolution | — | — |

#### 8-FSK Presets (12 modes)

| Preset | Baud | Base Freq | Spacing | Bandwidth |
|---|---|---|---|---|
| Mode 0 — FT8-style | 6 | 1000 Hz | 6.25 Hz | ~44 Hz |
| Mode 1 | 45 | 1500 Hz | 45 Hz | 315 Hz |
| Mode 2 — Wide | 45 | 1500 Hz | 90 Hz | 630 Hz |
| Mode 3 | 75 | 1500 Hz | 75 Hz | 525 Hz |
| Mode 4 — Wide | 75 | 1200 Hz | 150 Hz | 1050 Hz |
| Mode 5 | 100 | 1500 Hz | 100 Hz | 700 Hz |
| Mode 6 | 125 | 1200 Hz | 125 Hz | 875 Hz |
| Mode 7 | 150 | 1200 Hz | 150 Hz | 1050 Hz |
| Mode 8 | 200 | 1000 Hz | 200 Hz | 1400 Hz |
| Mode 9 | 250 | 800 Hz | 250 Hz | 1750 Hz |
| Mode 10 | 300 | 800 Hz | 300 Hz | 2100 Hz |
| Mode 11 | 350 | 800 Hz | 350 Hz | 2450 Hz |

#### 16-FSK Presets (6 modes)

| Preset | Baud | Base Freq | Spacing | Bandwidth |
|---|---|---|---|---|
| Mode 0 — MFSK16-style | 16 | 1000 Hz | 16 Hz | 240 Hz |
| Mode 1 | 25 | 1200 Hz | 25 Hz | 375 Hz |
| Mode 2 — Wide/Anti-Fade | 25 | 1200 Hz | 50 Hz | 750 Hz |
| Mode 3 | 50 | 1000 Hz | 50 Hz | 750 Hz |
| Mode 4 | 100 | 800 Hz | 100 Hz | 1500 Hz |
| Mode 5 | 125 | 600 Hz | 125 Hz | 1875 Hz |

---

## 🛡️ Forward Error Correction (FEC)

Select protection level based on channel noise conditions:

| Mode | Algorithm | Frame Size | Protection Level |
|---|---|---|---|
| **None** | Raw 8-bit data with clock-bit framing | 10-bit | Fastest, no protection |
| **Hamming (7,4)** | Corrects single-bit flips per nibble | 16-bit | Light noise |
| **Reed-Solomon (Sim)** | Triple Modular Redundancy logic | 24-bit | Heavy noise |
| **Convolutional (Viterbi)** | Soft-decision Viterbi decoder | 16-bit | Continuous background noise |
| **LDPC (16,8) Systematic** | Iterative bit-flipping decoder, 20 iterations | 16-bit | Critical/tactical links |

All FEC modes are available across 2-Tone FSK, 8-FSK, and 16-FSK modulation types.

---

## 📻 AGWPE TNC Server

Built-in AGWPE 1.0-compatible TCP server enabling direct integration with popular APRS client software over the audio modem as a virtual TNC.

**Compatible clients:** Xastir · APRSIS32 · UI-View32 · YAAC · APRSdroid · PinPoint APRS · and any AGW-compatible software.

**Supported AGWPE frame types:**

| Frame | Direction | Function |
|---|---|---|
| `R` | Server → Client | Version handshake |
| `G` | Server → Client | Port info |
| `g` | Server → Client | Per-port capability |
| `X` / `x` | Client → Server | Register / unregister callsign |
| `M` | Client → Server | Send Unproto (UI) frame via radio |
| `V` | Client → Server | Send Unproto VIA digipeater |
| `K` | Bidirectional | Raw AX.25 frame TX and RX monitoring |
| `D` | Client → Server | Send connected data |
| `T` | Client → Server | Heartbeat / keepalive |
| `m` / `k` | Client → Server | Enable UI monitor / raw AX.25 monitor |

**AGWPE Server window** now includes an integrated **Receiver Buffer**, **Audio Spectrum Waterfall**, and **Eye Diagram / Symbol Confidence** panel — allowing full signal monitoring directly inside the AGWPE configuration window without switching to the main TX/RX terminal.

---

## 📊 Signal Visualization

| Panel | Description |
|---|---|
| **Audio Spectrum Waterfall** | Real-time 2D frequency-time waterfall plot, auto-centered on active FSK tones. Available in TX/RX Terminal, Send File, and AGWPE windows. |
| **Eye Diagram** | Phosphor-style eye diagram with 200-trace persistence. Active in 2-Tone FSK mode. |
| **Symbol Confidence (Goertzel)** | Per-tone energy histogram via Goertzel DFT. Active in 8-FSK and 16-FSK modes. Shows real-time decoder confidence for all 8 or 16 tones. |

---

## ✨ Key Features

- **Multi-Window TX Interface**: Dedicated windows for *Send Text*, *Send File*, and *Send Image (MFSK)*, each with independent waterfall + eye/symbol visualization.
- **AGWPE TNC Server**: Full AX.25/APRS packet radio integration. The server window includes live Receiver Buffer, Waterfall, and Eye Diagram / Symbol Confidence — no need to switch windows while operating APRS.
- **Hamlib PTT (rigctld)**: Hardware PTT control via Hamlib `rigctld` daemon. Configurable IP, port, and PTT command. The modem automatically opens/closes PTT around each transmission.
- **Integrated BBS Server**: Automated Bulletin Board System with `/help` and `/request_berita` commands. Place `.txt` files in the `news` folder to broadcast them over radio.
  - **Windows path**: `news\` folder next to the `.exe`
  - **Android path**: `/storage/emulated/0/Documents/Tactical_FSK_Modem/news`
- **Send File**: Transmit arbitrary binary/text files over radio with byte-stuffed framing and optional FEC.
- **Send Image (MFSK)**: SSTV-style analog multi-tone image transmission at 720P vertical resolution.
- **Advanced DSP Audio**: Receiver **Automatic Gain Control (AGC)** with adjustable threshold, manual TX output gain, and auto-frequency centering for the waterfall.
- **Byte Stuffing Protocol**: Start/End-of-Frame markers (`0x02` / `0x04×3`) with escape-character stuffing (`0x1B`) for reliable framing over audio channels.
- **Civilian Build**: A stripped-down build variant without login, cryptography, or TAK Gateway — designed for open amateur radio and public safety use.

---

## 🛠️ Technical Details

| Parameter | Value |
|---|---|
| **Modulation** | 2-Tone FSK · 8-FSK · 16-FSK · MFSK Image |
| **Baud Rate** | 1 – 1200 bps (FSK) · 6 – 350 baud (8-FSK) · 16 – 125 baud (16-FSK) |
| **FEC** | None · Hamming(7,4) · Reed-Solomon(Sim) · Viterbi · LDPC(16,8) |
| **AX.25 / APRS** | AGWPE 1.0 TCP server, AX.25 UI frame encode/decode, callsign parsing |
| **PTT Control** | Hamlib rigctld (TCP), configurable host/port |
| **Signal Sync** | 1400 Hz → 1000 Hz → 1400 Hz VIS preamble |
| **Sample Rate** | 44100 Hz (standard) · 12000 Hz (8-FSK FT8-style mode) |
| **Frame Framing** | SOF `0xAA×4` + `0x02`, EOF `0x04×3`, ESC `0x1B` |
| **BBS Directory** | `news\` (Windows) · `Documents/Tactical_FSK_Modem/news` (Android) |
| **AGWPE Default Port** | 8000 |

---

## 🚀 How to Run

1. **Windows**: Run `FSK_Modem_GOV.exe` (or the civilian build `.exe`).
2. **Android**: Install the APK, grant Microphone and Storage permissions.
3. **Modulation**: Go to `Config > Modulation Configuration`, select FSK / 8-FSK / 16-FSK and the desired preset and FEC mode.
4. **APRS/TNC**: Open `Config > AGWPE Configuration`, enter your callsign and port (default 8000), click **START AGWPE SERVER**, then point your APRS client to the displayed Host IP and port.
5. **PTT**: Open `Config > Hamlib Configuration`, enable rigctld PTT, enter the rigctld host/port, and click **Connect**.
6. **BBS**: Place `.txt` files in the `news` folder. Clients can query them over radio using `/help` and `/request_berita`.
7. **Transmit**: Enter text in *Send Text*, select a file in *Send File*, or load an image in *Send Image*, then press **TRANSMIT PACKET (PTT)**.

---

**Developer Note:**
This project was independently developed by **YD1RUH** for tactical radio communication education and experimental digital signal processing (DSP).

© 2026 YD1RUH — **Tactical_FSK_Modem**
