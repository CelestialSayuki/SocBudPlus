# Socbud

**Socbud** is an advanced power and performance monitoring suite designed specifically for Apple Silicon devices.

It is capable of distinguishing between **Core Logic** and **SRAM** voltages—revealing the true, ultra-low power states of Apple Silicon that other tools miss.

The project is divided into two distinct product lines...

* **Socbud+**: A modern, beautiful GUI application built with SwiftUI and \"Liquid Glass\" design language.
* **Socbud+ TUI**: A lightweight, pure TUI tool for terminal enthusiasts and developers, providing granular data output with ASCII visualizations.

## 🚀 Download and Installation

**This software is for internal preview only. Please join the QQ Group to receive the download link and the latest version!**

**Official QQ Group: [Click here to join the infodrop.cn QQ Group](https://infodrop.cn/?open=auth)**

**To ensure software stability and prevent unauthorized distribution during the beta phase, mandatory online authentication is required upon launch.**

* **Data Collection**: The software will collect your device's Chip Model (and basic IORep structure for debugging) to validate compatibility.
* **Requirement**: You must accept the license agreement and have an active internet connection to run.
* **Privacy**: No personal data beyond hardware identifiers is collected.

---

## 🌟 Feature Matrix & Distributions

We provide some distinct distributions across macOS and iOS platforms:

| Feature | macOS: **Socbud+** (GUI) | macOS: **Socbud+ TUI** | iOS: **Socbud+** | iOS: **Socbud+-JB** | iOS: **Socbud+ TUI** |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Type** | Desktop App | Binary Tool | Sideload App | Jailbreak App | Binary Tool |
| **Interface** | Liquid Glass UI | TUI | Liquid Glass UI | Liquid Glass UI | TUI |
| **Visual Charts** | ✅ | ✅ (ASCII) | ✅ | ✅ | ✅ (ASCII) |
| **Raw Data Dump** | ❌ | ✅ | ❌ | ❌ | ✅ |
| **Remote Monitor** | Host / Client | Host Only | Client Only | Client / Host | Host Only |
| **Legacy OS** | ❌ | ✅ | ❌ | ❌ | ✅ |
> **Note**: **iOS Socbud+** is designed for standard signing, which only act as a client. **Socbud+-JB** is optimized for Jailbroken environments (Rootful/Rootless) with extended entitlements.

## 🛠️ System Requirements

| Component | Requirement |
| :--- | :--- |
| **Architecture** | Apple Silicon |
| **Socbud+ (GUI)** | **macOS 13.0+** (Ventura) or **iOS 16.0+** |
| **Socbud+ TUI** | **macOS 11.0+** (Big Sur) or **iOS 13.0+** |

## ✅ Chip Support Status

While Socbud can detect the model identity of almost all Apple Silicon devices, full power telemetry requires specific hardware sensor mapping.

### Apple M-Series

| Chip Model | Status | Capability |
| :--- | :---: | :--- |
| **M1** | 🟢 **Supported** | Full Telemetry. |
| **M1 Pro** | 🟢 **Supported** | Full Telemetry. |
| **M1 Max** | 🟢 **Supported** | Full Telemetry. |
| **M1 Ultra** | ⚪ **Pending** | Power sensors dump pending. |
| **M2** | 🟢 **Supported** | Full Telemetry. |
| **M2 Pro** | ⚪ **Pending** | Power sensors dump pending. |
| **M2 Max** | 🟢 **Supported** | Full Telemetry. |
| **M2 Ultra** | 🟡 **Unknown** | Unknown |
| **M3**| 🟢 **Supported** | Full Telemetry. |
| **M3 Pro**| 🟢 **Supported** | Full Telemetry. |
| **M3 Max**| 🟢 **Supported** | Full Telemetry. |
| **M3 Ultra** | 🟡 **Unknown** | Unknown |
| **M4 Family** | 🟢 **Supported** | Full Telemetry. |
| **M5** | 🟢 **Supported** | Full Telemetry. |

### Apple A-Series

| Chip Model | Status | Capability |
| :--- | :---: | :--- |
| **A19 / Pro** | ⚪ **Pending** | Power sensors dump pending. |
| **A18 / Pro** | ⚪ **Pending** | Power sensors dump pending. |
| **A17 Pro** | ⚪ **Pending** | Power sensors dump pending. |
| **A16 Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A15 Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A14 Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A13 Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A12X / A12Z Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A12 Bionic** | ⚪ **Pending** | Power sensors dump pending. |
| **A11 Bionic** | 🟢 **Supported** | Full Telemetry. |
| **A10X Fusion** | ⚪ **Pending** | Power sensors dump pending. |
| **A10 Fusion** | ⚪ **Pending** | Power sensors dump pending. |
| **A9X** | ⚪ **Pending** | Power sensors dump pending. |
| **A9** | ⚪ **Pending** | Power sensors dump pending. |
| **A8X** | ⚪ **Pending** | Power sensors dump pending. |
| **A8** | ⚪ **Pending** | Power sensors dump pending. |

## 🖥️ Socbud+ TUI Usage

The **Socbud+ TUI** version is a standalone binary that provides detailed telemetry identical to low-level engineering tools, wrapped in a responsive Text User Interface.

**Note:** You do **not** need `sudo` to run this tool. It works with standard user privileges as long as the binary is correctly signed with the necessary entitlements.

### Basic Command

```bash
# Run with default settings
./socbud
```

### Controls & Navigation

*   **ARROWS**: Select Clusters or Cores.
*   **ENTER**: View detailed breakdown (DVFS tables & ASCII Charts).
*   **1 / 2 / 3**: Set refresh rate to 0.5s / 1.0s / 2.0s.
*   **7 / 8 / 9**: Set chart history to 60s / 180s / 300s.
*   **Q**: Quit.

### Output Explanation

The TUI outputs a structured view of the SoC's power state:

* **Unmapped E**: Power rails not assigned to specific cores (System overhead).
* **ANE**: Apple Neural Engine frequency and voltage.
* **Clusters**: Detailed breakdown of E-Cores and P-Cores, including:
    * Frequency (MHz)
    * **Voltage (mV)**: Displays both **Logic** (Active Core) and **SRAM** (Cache) voltages separately when available.
    * Power (W)
    * Residency (Active vs Idle %)
    * **DVFS Distribution**: A histogram of time spent at each frequency state.

## 📱 Socbud+ (GUI) Usage

### Local Monitoring
Simply launch the app. The dashboard will visualize real-time metrics using the adaptive Liquid Glass interface.

### Remote Monitoring (Cross-Device)
Turn your iPhone/iPad into a dedicated dashboard for your Mac:

1.  Ensure both devices are on the same LAN/Wi-Fi.
2.  **Host**: Run GUI or TUI Version on the device you want to monitor.
3.  **Client**: Run **Socbud+** on your viewing device (iOS/macOS).
4.  Tap the device menu in the header and select the Host.

## ⚠️ Disclaimer

This project utilizes Apple's private framework (`IOReport`) and undocumented APIs.

* **For educational and research purposes only.**
* Do not use in production environments or submit to the App Store.
* Low-level hardware sensor reading capabilities may break with system updates.

## 🚫 Source Code Status: Closed Source

**IMPORTANT: This project is Closed Source.**

Please **DO NOT** share or reverse-engineer this software in any public setting. All downloads and updates are provided exclusively through designated channels.

## 📄 License

This project is licensed under the **Celestia-no-mad-world License**. 

By using this software, you agree to the terms of the Preview Experience Program.

*Built with ❤️ by CelestialSayuki*
