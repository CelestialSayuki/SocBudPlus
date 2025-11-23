# Socpowerbud XT

**Socpowerbud XT** is an advanced power and performance monitoring suite designed specifically for Apple Silicon devices.

The project is divided into two distinct product lines to cater to different needs:

* **Socpowerbud XTs**: A modern, beautiful GUI application built with SwiftUI and \"Liquid Glass\" design language.
* **Socpowerbud XT**: A lightweight, pure CLI tool for terminal enthusiasts and developers, providing granular data output.

## 🚀 Download and Installation

**This software is for internal preview only. Please join the QQ Group to receive the download link and the latest version!**

**Official QQ Group: [Click here to join the infodrop.cn QQ Group](https://infodrop.cn/?open=auth)**

**To ensure software stability and prevent unauthorized distribution during the beta phase, mandatory online authentication is required upon launch.**

* **Data Collection**: The software will collect your device's Chip Model (and basic IORep structure for debugging) to validate compatibility.
* **Requirement**: You must accept the license agreement and have an active internet connection to run.
* **Privacy**: No personal data beyond hardware identifiers is collected.

---

## 🌟 Feature Matrix & Distributions

We provide **5 distinct distributions** across macOS and iOS platforms:

| Feature | macOS: **XTs** (GUI) | macOS: **XT** (CLI) | iOS: **XTs** | iOS: **XTs-JB** | iOS: **XT** (CLI) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Type** | Desktop App | Binary Tool | Sideload App | Jailbreak App | Binary Tool |
| **Interface** | Liquid Glass UI | Text / Stdout | Liquid Glass UI | Liquid Glass UI | Text / Stdout |
| **Visual Charts** | ✅ | ❌ | ✅ | ✅ | ❌ |
| **Raw Data Dump** | ❌ | ✅ | ❌ | ❌ | ✅ |
| **Remote Monitor** | Host / Client | Host Only | Client Only | Client / Host | Host Only |
| **Legacy OS** | ❌ | ✅ | ❌ | ❌ | ✅ |
| **Root/Sudo** | Not Required | Not Required | Not Required | Not Required | Not Required |

> **Note**: **iOS XTs** is designed for TrollStore or standard signing. **iOS XTs-JB** is optimized for Jailbroken environments (Rootful/Rootless) with extended entitlements.

## 🛠️ System Requirements

| Component | Requirement |
| :--- | :--- |
| **Architecture** | Apple Silicon |
| **Socpowerbud XTs (GUI)** | **macOS 13.0+** (Ventura) or **iOS 16.0+** |
| **Socpowerbud XT (CLI)** | **macOS 11.0+** (Big Sur) or **iOS 11.0+** |

## ✅ Chip Support Status

While Socpowerbud XT can detect the model identity of almost all Apple Silicon devices, full power telemetry requires specific hardware sensor mapping.

### Apple M-Series

| Chip Model | Status | Capability |
| :--- | :---: | :--- |
| **M1** | ⚪ **Pending** | Power sensors pending. |
| **M1 Pro** | 🟢 **Supported** | Full Telemetry. |
| **M1 Max** | 🟢 **Supported** | Full Telemetry. |
| **M1 Ultra** | ⚪ **Pending** | Power sensors pending. |
| **M2** | 🟢 **Supported** | Full Telemetry. |
| **M2 Pro** | ⚪ **Pending** | Power sensors pending. |
| **M2 Max** | 🟢 **Supported** | Full Telemetry. |
| **M2 Ultra** | ⚪ **Pending** | Power sensors pending. |
| **M3**| 🟢 **Supported** | Full Telemetry. |
| **M3 Pro**| 🟢 **Supported** | Full Telemetry. |
| **M3 Max**| 🟡 **Partial** | T6034 Power sensors pending. |
| **M3 Ultra**| ⚪ **Pending** | Power sensors pending. |
| **M4** | 🟢 **Supported** | Full Telemetry. |
| **M4 Pro** | 🟢 **Supported** | Full Telemetry. |
| **M4 Max** | 🟢 **Supported** | Full Telemetry. |
| **M5** | 🟢 **Supported** | Full Telemetry. |

### Apple A-Series

| Chip Model | Status | Capability |
| :--- | :---: | :--- |
| **A19 / Pro** | ⚪ **Pending** | Power sensors pending. |
| **A18 / Pro** | ⚪ **Pending** | Power sensors pending. |
| **A17 Pro** | ⚪ **Pending** | Power sensors pending. |
| **A16 Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A15 Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A14 Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A13 Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A12X / A12Z Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A12 Bionic** | ⚪ **Pending** | Power sensors pending. |
| **A11 and older** | ⚪ **Pending** | Power sensors pending. |

## 🖥️ Socpowerbud XT (CLI) Usage

The CLI version is a standalone binary that provides detailed telemetry identical to low-level engineering tools. 

**Note:** You do **not** need `sudo` to run this tool. It works with standard user privileges as long as the binary is correctly signed with the necessary entitlements.

### Basic Command

```bash
# Run with default settings (1.0s refresh)
./socpowerbud-xt

# Run with a specific refresh interval (e.g., 0.5 seconds)
./socpowerbud-xt -i 0.5
```

### Output Explanation

The CLI outputs a structured view of the SoC's power state:

* **Unmapped E**: Power rails not assigned to specific cores (System overhead).
* **ANE**: Apple Neural Engine frequency and voltage.
* **Clusters**: Detailed breakdown of E-Cores and P-Cores, including:
    * Frequency (MHz)
    * Voltage (mV)
    * Power (mW)
    * Residency (Active vs Idle %)
    * **DVFS Distribution**: A histogram of time spent at each frequency state.
                    
## 📱 Socpowerbud XTs (GUI) Usage

### Local Monitoring
Simply launch the app. The dashboard will visualize real-time metrics using the adaptive Liquid Glass interface.

### Remote Monitoring (Cross-Device)
Turn your iPhone/iPad into a dedicated dashboard for your Mac:

1.  Ensure both devices are on the same LAN/Wi-Fi.
2.  **Host**: Run **XTs** (macOS) or **XT** (CLI) on the device you want to monitor.
3.  **Client**: Run **XTs** on your viewing device (iOS/macOS).
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
