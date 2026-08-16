<div align="center">

<img src="assets/ula.jpg" width="96" style="border-radius:20px" alt="ULA Proxy"/>

# ULA Proxy

**Virtual network manager for Windows**
*Connect devices over the internet as if they're on the same local network*

[![.NET 8](https://img.shields.io/badge/.NET-8.0-512BD4?style=flat-square&logo=dotnet)](https://dotnet.microsoft.com/)
[![Platform](https://img.shields.io/badge/platform-Windows-0078D4?style=flat-square&logo=windows)](https://www.microsoft.com/windows)
[![License](https://img.shields.io/badge/license-MIT-22C55E?style=flat-square)](LICENSE)

</div>

---

##  Features

-  **Virtual LAN** — create or join encrypted virtual networks instantly
-  **Peer discovery** — real-time list of connected devices with ping and IP
-  **CLI** — full control from any terminal via `ula` command
-  **Toast notifications** — peer join/leave events in real time
-  **Activity logs** — real-time log viewer with export to file
-  **Localization** — English and Russian interface

---

##  Requirements

- Windows 10/11 x64
- [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)

---

##  Start

1. Download `ULAProxy.exe` from [Releases](../../releases)
2. Run it — `ula` CLI installs automatically to `C:\ULAProxy\` and is added to PATH
3. Open a new terminal and type `ula --help`

---

##  CLI Reference

```
Window:
  ula --open               Open ULA Proxy window
  ula --close              Close ULA Proxy completely

Network:
  ula --connect <id> [pw]  Join a network by ID
  ula --create <name> [pw] Create a new network
  ula --leave              Leave current network
  ula --list               List available public networks
  ula --peers              Show connected peers
  ula --ip                 Show your virtual IP

Info:
  ula --status             Show running status + server info
  ula --version            Show version
  ula --help               Show this help
```

---

##  Window Behavior

| Action | Result |
|--------|--------|
| Click ✕ | Hides to background — process stays alive, no tray icon |
| Ctrl + ✕ | Fully exits the process |
| `ula --open` | Brings the window back from background |

---

## 🔨 Build from Source

```bash
git clone https://github.com/YOUR_USERNAME/ula-proxy.git
cd ula-proxy/ULA-Proxy
dotnet publish ULAProxy.csproj -c Release -r win-x64 --no-self-contained -o bin/publish
```

Output: `bin/publish/ULAProxy.exe`

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| UI | C# / WPF / .NET 8 |
| Networking | WebSocket relay server |
| Virtual adapter | WinTun |
| CLI ↔ App IPC | Named Pipes |
| Settings | JSON (`C:\ULAProxy\settings.json`) |
| Logs | `C:\ULAProxy\ula.log` |

---

<div align="center">
<sub>Built with ❤️ — ULA Proxy © 2025</sub>
</div>
