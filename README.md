# ⚡ RLX - RL-ProcessTamer

<div align="center">

[![Brand](https://img.shields.io/badge/Brand-Riswan--Limaga%20Experience%20(RLX)-blue?style=for-the-badge&logo=code)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-Windows%20Win32%20%7C%20C++-lightgrey?style=for-the-badge&logo=windows)](https://github.com)
[![RAM Usage](https://img.shields.io/badge/RAM%20Usage-%3C%203MB-success?style=for-the-badge)](https://github.com)

**A lightning-fast, zero-bloat background daemon engineered to eliminate CPU stutter on budget and low-end multi-core processors.**

</div>

---

## 🚀 Why RL-ProcessTamer?
On dual-core or budget processors (such as the Intel Core i3-2100), heavy background tasks (updates, indexing, browser tabs) frequently spike to 100% CPU usage, causing active windows and games to freeze. 

**RL-ProcessTamer** runs silently in the background as a native Win32 daemon. It monitors your active foreground window every few seconds and automatically lowers the priority (`Below Normal`) and restricts the CPU affinity (`Cores 2 & 3`) of background processes, leaving your core processing power dedicated to what matters.

## ✨ Key Features
* **Zero Bloat & Micro Footprint:** Written purely in native C++ using Win32 system APIs with **zero external dependencies** and less than 3MB RAM usage.
* **Smart Thread Balancing:** Automatically reserves primary threads for your active application.
* **Silent Background Daemon:** Runs invisibly with no distracting console windows or tray clutter.
* **Real-Time Logging:** Writes clean, timestamped actions to `rlx_tamer.log`.
* **Startup Persistence:** Automatically registers itself to run with Windows via the user registry (`HKCU`).

## 🛠️ Build from Source
If you have `g++` (MinGW-w64) installed, compile the native binary with maximum optimizations (`-O3`):

```cmd
g++ main.cpp -o RL-ProcessTamer.exe -O3 -luser32