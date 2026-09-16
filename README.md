<p align="right">
  <a href="README_FA.md"> <strong>فارسی</strong></a>
</p>

---

# Windows NCSI & Internet Probing Manager

A lightweight Windows utility consisting of Registry tweaks and a self-elevating Batch script designed to manage the **Network Connectivity Status Indicator (NCSI)** Active Probing feature and restart the Network Location Awareness (`NlaSvc`) service.

It resolves common Windows issues such as false "No Internet Access" alerts (globe icon or yellow exclamation mark when the internet is actually working), eliminates unexpected captive-portal browser popups, and provides privacy control over periodic Microsoft network probing requests.

---

## 📁 Repository Contents

| File | Type | Description |
| :--- | :--- | :--- |
| **`Restart Network Service.bat`** | Batch Script | Automatically requests Administrator rights and restarts the `NlaSvc` service (and dependencies) to apply changes immediately. |
| **`Enable Internet Probing.reg`** | Registry File | Sets `EnableActiveProbing = 1` to restore the default Windows network connectivity checks. |
| **`Disable Internet Probing.reg`** | Registry File | Sets `EnableActiveProbing = 0` to stop Windows from polling `msftconnecttest.com`. |

---

## ✨ Features

- **🔑 Automatic Elevation (UAC):** The batch file detects privilege levels and automatically requests Administrator access via PowerShell.
- **⚡ Instant Effect Without Reboot:** Restarts `NlaSvc` with dependent services forced (`/y`), refreshing the system tray network indicator in seconds without restarting the computer.
- **🌐 Fixes False "No Internet" Icon:** Resolves cases where browsers and apps can connect to websites, but Windows incorrectly reports "No Internet, secured".
- **🛡️ Privacy & Telemetry Management:** Disables recurring HTTP polling to Microsoft servers (`msftconnecttest.com` and `ipv6.msftconnecttest.com`).
- **📦 Clean & Native:** 100% native Windows files with zero external dependencies.

---

## 🚀 How to Use

### Step 1: Choose Your Desired Configuration
- To **disable** internet probing (fix false captive portals / stop telemetry):  
  Double-click **`Disable Internet Probing.reg`** and click **Yes** to merge.
- To **restore default** internet probing:  
  Double-click **`Enable Internet Probing.reg`** and click **Yes** to merge.

### Step 2: Apply Changes
- Double-click **`Restart Network Service.bat`**.
- Accept the **UAC** prompt when prompted.
- The script will stop and restart the network service. The network tray icon will refresh automatically within 5 seconds.

---

## 💻 System Requirements

- **OS:** Windows 7, Windows 8.1, Windows 10, or Windows 11.
- **Permissions:** Administrator access (handled automatically by the batch script).
