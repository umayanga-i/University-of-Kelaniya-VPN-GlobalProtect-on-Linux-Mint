# 🎓 University of Kelaniya VPN Connector (Linux Mint)

A simple Bash script to connect to the **University of Kelaniya GlobalProtect VPN**
using **OpenConnect** on Linux Mint / Ubuntu-based systems.

🌐 Portal: `gp.kln.ac.lk`  
🔐 Protocol: GlobalProtect (gp)

---

## 🚀 Features

- ✅ Automatic check for OpenConnect
- ✅ Simple username prompt
- ✅ Secure password entry
- ✅ Easy disconnect (CTRL + C)
- ✅ Works on Linux Mint & Ubuntu

---

## 📦 Requirements

- Linux Mint / Ubuntu-based Linux
- Internet connection
- University VPN credentials

---

## 🛠 Installation

### 1️⃣ Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
```

Or download ZIP and extract.

---

### 2️⃣ Make Script Executable

```bash
chmod +x connect-vpn.sh
```

---

## ▶ Usage

Run:

```bash
./connect-vpn.sh
```

You will be prompted for:

```
Username:
Password:
```

⚠ Password will not be visible while typing (this is normal).

---

## 🔌 Disconnect VPN

Press:

```
CTRL + C
```

---

## 🔧 Manual Install (If Needed)

If OpenConnect is not installed:

```bash
sudo apt update
sudo apt install openconnect
```

---

## ❗ Troubleshooting

If you see errors like:

- `Failed to open HTTPS connection`
- `No route to host`
- Certificate warning

Make sure:

- Internet connection is active
- Portal address is correct: `gp.kln.ac.lk`
- You typed correct username/password

---

## 🧑‍💻 Tested On

- Linux Mint 21+
- Ubuntu 22.04+
- OpenConnect (GlobalProtect protocol)

---

## 📌 Credits

- OpenConnect Project
- Palo Alto GlobalProtect
- University of Kelaniya IT Services

---

## ⚠ Disclaimer

This project is not officially affiliated with the University of Kelaniya.
Use at your own responsibility.
