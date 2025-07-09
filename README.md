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

- ✅ Fully automated installer for all tools
- ✅ Sends secure `NEWNYM` signals without restarting Tor
- ✅ Sets up cookie-based authentication (no password needed)
- ✅ Prompts for user-defined IP change interval (e.g., every 5 minutes)
- ✅ Installs a persistent **systemd service** to run on startup

---
## Supported Distributions(tested)

- Arch Linux / Manjaro
- Debian / Ubuntu
- Kali Linux
- Parrot OS
- Fedora
- OpenSUSE


---
## 🚀 Quick Install

```
git clone https://github.com/abdullah-x909/Tor-ip-changer.git
cd Tor-ip-changer
chmod +x setup.sh
./setup.sh
```
---

## 🛠 How It Works

1. Install and setup Tor
2. Configures Tor control port at 9051 with cookie authentication
3. Adds your user to the correct group (debian-tor)
4. Starts the script on system boot
5. Authenticates to Tor via control port
---


## Usage

Once installed, the service will automatically start and run in the background. Your IP address will be changed at the interval you specified during installation.

### Checking Status

To check if the service is running:
```bash
systemctl status change-tor-ip.service
```

## Uninstallation

To remove the IP Changer:
```bash
sudo systemctl stop change-tor-ip.service
sudo systemctl disable change-tor-ip.service
sudo systemctl stop tor
sudo systemctl disable tor
sudo rm /etc/systemd/system/change-tor-ip.service
sudo rm /home/$USER/change_tor_ip.sh
```

## Security Note

This tool uses the Tor network to change your IP address. While Tor provides anonymity, please be aware that:
- Some websites may block Tor exit nodes
- Your connection speed may be affected
- Always use HTTPS connections for sensitive data



## Donate 
for more repo Donate here [paypal](https://www.paypal.com/ncp/payment/7BPCFFBTG9QYY)
