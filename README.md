<h1 align="center">🛡️ Tor IP Rotator – Secure NEWNYM-Based Exit IP Changer</h1>

<p align="center">
  <img src="https://img.shields.io/github/license/abdullah-x909/tor-ip-changer?style=flat-square" />
  <img src="https://img.shields.io/github/stars/abdullah-x909/tor-ip-changer?style=flat-square" />
  <img src="https://img.shields.io/github/forks/abdullah-x909/tor-ip-changer?style=flat-square" />
  <img src="https://img.shields.io/badge/Tor-Exit%20Node%20Changer-purple?style=flat-square" />
</p>

<p align="center"><b>Securely rotate your Tor exit IP using the official control API — no service restart needed!</b></p>

---

## 🔒 About This Project

**Tor IP Rotator** is a lightweight, fully automated tool that safely rotates your Tor exit IP by sending the official `NEWNYM` signal via Tor's control port.  
It’s more secure than restarting the Tor service and avoids reusing circuits — ideal for OSINT, penetration testing, or maintaining anonymity.

---

## ✨ Features

- ✅ Fully automated installer: supports Debian, Ubuntu, Kali, Arch, Manjaro, Fedora
- ✅ Sends secure `NEWNYM` signals without restarting Tor
- ✅ Uses [Stem](https://stem.torproject.org/) — Tor’s official Python controller
- ✅ Sets up cookie-based authentication (no password needed)
- ✅ Prompts for user-defined IP change interval (e.g., every 5 minutes)
- ✅ Optionally installs a persistent **systemd service** to run on startup
- ✅ Shows current exit IP after each rotation

---
##✅ **Requirements**

  -- Linux OS (Debian, Ubuntu, Kali, Arch, Manjaro, Fedora tested)

  -- Python 3

  -- Tor

  -- pip (python3-pip)


---
## 🚀 Quick Install

```
git clone https://github.com/abdullah-x909/tor-ip-rotator.git
cd tor-ip-rotator
chmod +x tor-ip-rotator.sh
./tor-ip-rotator.sh
```
---

## 🛠 How It Works

1. Installs tor and Python stem library (if missing)
2. Configures Tor control port at 9051 with cookie authentication
3. Adds your user to the correct group (debian-tor)
4. Starts a background Python script that:
5. Authenticates to Tor via control port

     -- Sends SIGNAL NEWNYM to request a new identity

     -- Displays current exit IP

     -- Sleeps and repeats after given interval

---

##🔁 Manual Usage

After initial setup, to manually rotate IPs:

  `~/.tor-ip-rotator/rotate.py`

To view exit IP at any time:

  `tor-resolve www.google.com`

---

##🔧 systemd Auto-Start (Optional)

If you allow it, the installer creates a persistent background service:

  `~/.config/systemd/user/tor-ip-rotator.service`

Manage it with:

```
systemctl --user enable tor-ip-rotator
systemctl --user start tor-ip-rotator
systemctl --user stop tor-ip-rotator
```

---
