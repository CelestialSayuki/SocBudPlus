# Socpowerbud XT

**Socpowerbud** is an advanced power and performance monitoring suite designed specifically for Apple Silicon devices.

The project is divided into two distinct product lines to cater to different needs:

* **Socpowerbud XTs**: A modern, beautiful GUI application built with SwiftUI and \"Liquid Glass\" design language.
* **Socpowerbud XT**: A lightweight, pure CLI tool for terminal enthusiasts and developers, providing granular data output.

## ⚠️ Preview Experience Program

**This software is currently in a Preview state.**

To ensure software stability and prevent unauthorized distribution during the beta phase, **mandatory online authentication** is required upon the first launch.

* **Data Collection**: The software will collect your device's Serial Number and Chip Model (and basic IORep structure for debugging) to validate compatibility.
* **Requirement**: You must accept the license agreement and have an active internet connection for the initial run.
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
| **Architecture** | Apple Silicon (M1/M2/M3/M4/A-Series) |
| **Socpowerbud XTs (GUI)** | **macOS 13.0+** (Ventura) or **iOS 16.0+** |
| **Socpowerbud XT (CLI)** | **macOS 11.0+** (Big Sur) or **iOS 11.0+** |

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
3.  **Client**: Run **XTs** on your viewing device (iOS/macOS).\n4.  Tap the device menu in the header and select the Host.

## ⚠️ Disclaimer

This project utilizes Apple's private framework (`IOReport`) and undocumented APIs.

* **For educational and research purposes only.**
* Do not use in production environments or submit to the App Store.
* Low-level hardware sensor reading capabilities may break with system updates.

## 📄 License

This project is open-sourced under the **Celestia-no-mad-world License**. 

By using this software, you agree to the terms of the Preview Experience Program.

---

*Built with ❤️ by CelestialSayuki*
