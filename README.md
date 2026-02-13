# 🎓 University of Kelaniya VPN (GlobalProtect) on Linux Mint

This guide explains how to connect to the **University of Kelaniya VPN**
using **OpenConnect (GlobalProtect protocol)** on Linux Mint.

Portal Address:
```
gp.kln.ac.lk
```

---

## 🛠 Requirements

- Linux Mint (Ubuntu-based)
- Terminal access
- University VPN username & password

---

## 📦 Step 1 — Install Required Packages

Open Terminal and run:

```bash
sudo apt update
sudo apt install openconnect network-manager-openconnect network-manager-openconnect-gnome
```

Restart NetworkManager:

```bash
sudo systemctl restart NetworkManager
```

Or simply reboot your system.

---

## 🔐 Step 2 — Connect to VPN

Run:

```bash
sudo openconnect --protocol=gp gp.kln.ac.lk
```

If you want to specify username:

```bash
sudo openconnect --protocol=gp --user=YOUR_USERNAME gp.kln.ac.lk
```

Replace:

```
YOUR_USERNAME
```

with your university username.

---

## 🖥 Authentication

You will be prompted for:

```
Username:
Password:
```

⚠ Password will not be visible while typing (this is normal).

If certificate warning appears:

Type:

```
yes
```

---

## ✅ Successful Connection

If connected successfully, you will see:

```
ESP tunnel connected; exiting HTTPS mainloop.

```

Your VPN is now active 🎉

---
# Create Script File
---
#### Create Script File

Create a file named:

```
connect-vpn-auto.sh
```

Paste the following inside:

```bash
#!/bin/bash

PORTAL="gp.kln.ac.lk"

# 🔐 ENTER YOUR CREDENTIALS HERE
USERNAME="YOUR_USERNAME"
PASSWORD="YOUR_PASSWORD"

echo "Connecting to University of Kelaniya VPN..."

echo "$PASSWORD" | sudo openconnect --protocol=gp --user="$USERNAME" --passwd-on-stdin $PORTAL

echo "VPN Disconnected."
```

---

#### Add Your Credentials

Replace:

```
YOUR_USERNAME
YOUR_PASSWORD
```

Example:

```bash
USERNAME="it12345"
PASSWORD="MySecurePassword123"
```

---

#### Make Script Executable

```bash
chmod +x connect-vpn-auto.sh
```

---








## 🔌 Disconnect VPN


Close terminal

OR

If you already have a stuck connection right now

Run this to force disconnect:
```
sudo pkill -f "openconnect.*gp.kln.ac.lk"

```
or (more aggressive):
```
sudo pkill openconnect
```


---

## ❗ Troubleshooting

If you get errors like:

- `Failed to open HTTPS connection`
- `SAML authentication required`
- `No route to host`

Make sure:

- Internet is working
- Portal address is correct: `gp.kln.ac.lk`
- Packages are installed correctly

---

## 🧑‍💻 Tested On

- Linux Mint 21+
- OpenConnect (GlobalProtect protocol)

---

## 📌 Credits

- OpenConnect project
- Palo Alto GlobalProtect VPN
- University of Kelaniya IT Services
