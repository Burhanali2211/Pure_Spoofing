# 🛡 External SSD Privacy OS Setup

This project provides a complete, privacy-hardened Linux environment on an external SSD.  
The goal is to create a portable, secure development OS where your main machine stays untouched and no data leaks occur.

---

## 🚀 **What this does**
- Installs a privacy-respecting Linux OS (example: Linux Mint) on your external SSD
- Sets up Node.js, VSCodium (telemetry-free VSCode), and essential tools
- Configures a firewall to block unwanted network traffic
- Disables telemetry, auto-updates, and analytics

---

## 📦 **Requirements**
- External SSD or high-speed USB (recommended: SSD for performance)
- A blank USB drive (to create the live Linux installer)
- A computer that supports booting from USB/external SSD
- Internet connection (for initial setup + downloads)

---

## ⚠ **DISCLAIMER**
Be *very careful* when choosing your drive during installation. If you choose the wrong device, you could wipe your main system!

---

## 📝 **Installation steps**

### 1️⃣ Clone this repository  
```bash
git clone https://github.com/Burhanali2211/pure_spoof.git
cd pure_spoof

###2️⃣ Create a live Linux installer
Download the ISO (e.g. Linux Mint 21.3 Cinnamon 64-bit):
https://linuxmint.com/download.php

Use a tool like Rufus, Ventoy, or balenaEtcher to write the ISO to a USB stick

###3️⃣ Boot into the live Linux environment
Insert the live USB and reboot your machine
Enter the BIOS/boot menu (often F12, F10, or Esc)
Choose the USB stick as boot device

###4️⃣ Prepare your external SSD
Open terminal:

```bash
sudo gparted

In GParted:

Select your external SSD (⚠ double-check it’s the correct device)

Create a new GPT partition table

Create a large ext4 partition (use entire disk)

(Optional: create a small 512MB FAT32 EFI partition for UEFI systems)

Apply changes


###5️⃣ Run the Linux installer
Launch Install Linux Mint

Choose:

Installation type: Something else

Mount your ext4 partition as /

Mount your EFI partition as /boot/efi if you created one

Set the bootloader to the external SSD (e.g. /dev/sdb)

Set your username, hostname, password

Complete installation

###6️⃣ Boot into your external SSD
Remove the live USB

Reboot and select the external SSD as boot device in BIOS

