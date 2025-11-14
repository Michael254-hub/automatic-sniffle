Replacing Windows 11 with **Linux - Ubuntu**, going step-by-step carefully so you don’t lose important data or brick your system.

Here's a walk through the **full process of what I did safely** 👇

---

## ⚠️ Step 0: Before I Started

### Backing up Everything Important

1. Copy your important files (documents, pictures, downloads, etc.) to:

   * An external hard drive, or
   * A cloud storage (Google Drive, OneDrive)
2. Make sure your Windows license key (if you ever want to reinstall Windows later) is saved.

   * Run this command in PowerShell:

     ```bash
     wmic path softwarelicensingservice get OA3xOriginalProductKey
     ```
   * Save the key somewhere safe.

Unfortunately, I had nth important on my side to backup!
---

## 🧰 Step 1: Choosing Your Linux Distribution

Pick a distro (version) of Linux that suits your use:

| Purpose           | Recommended Distro                             |
| ----------------- | ---------------------------------------------- |
| Beginner friendly | **Ubuntu** or **Linux Mint**                   |
| Lightweight       | **Lubuntu**, **Xubuntu**, or **Zorin OS Lite** |
| Developer focused | **Fedora**, **Ubuntu**, or **Pop!_OS**         |
| Privacy/Security  | **Debian**, **Tails**, or **Qubes OS**         |

I chose Ubuntu for being developer focused and beginner friendly.

---

## 💾 Step 2: Create a Bootable USB

1. Download the **ISO image** of your chosen Linux distro (from its official website).

   * Example: [https://ubuntu.com/download](https://ubuntu.com/download)
2. Plug in a USB drive (at least 8GB).
3. Use a tool like:

   * **Rufus** (on Windows)
   * **Balena Etcher** (cross-platform) - used it after downloading from [etcher.io](etcher.io) - official platform.

4. Opened **balenaEtcher** → Selected my ISO image → Chose the drive → Flashed.

5. Click **Start** to create the bootable USB.

If I would have used **Rufus**, the following would have been the processes:

4. Open **Rufus** → Select your USB → Choose the ISO → Set Partition scheme:

   * **GPT for GUID Partition Table** for UEFI systems (most modern PCs)
   * **MBR for Master Boot Recorder** for Legacy BIOS
5. Click **Start** to create the bootable USB.

---

## ⚙️ Step 3: Boot from USB

1. Restart your PC.
2. Immediately press your **boot key** (depending on manufacturer):

   | Brand  | Key       |
   | ------ | --------- |
   | HP     | Esc or F9 |
   | Dell   | F12       |
   | Lenovo | F12       |
   | Acer   | F12       |
   | Asus   | F8        |
3. Select your USB drive from the boot menu.

You’ll now enter the **Linux Live Environment**, where you can try Linux without installing it yet.

---

## 💿 Step 4: Install Linux and Remove Windows

1. On the desktop, I double-clicked **“Install Linux”** or **“Install Ubuntu”**.
2. Chose my **language and keyboard layout**.
3. When asked about installation type, I chose (Erase disk and Install Linux but still there was an option to dUAL BOOT alongside Windows 10 which I didn't want):

   * Selected **“Erase disk and install Linux”**.
   * This **completely deleted Windows 11** and all its partitions.
4. Select my **time zone**.
5. Entered my **name, computer name, username, and password**.
6. Click **Install Now**.

🧠 **Note:** The installer will automatically handle partitioning for you. (My preferrable choice since I'm not that advanced)
If you want manual control, you can choose “Something else,” but for most users, the automatic erase-and-install option is easiest.

---

## 🔁 Step 5: Reboot into Linux

1. Once installation was complete, I removed my USB drive when prompted.
2. My PC did boot directly into my new Linux system. 🎉

---

## 🌐 Step 6: Post-Installation Setup

After logging in:

1. Updated my system:

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Installed useful software:

   ```bash
   sudo apt install git curl vim build-essential gnome-tweaks
   ```
3. If needed, install proprietary drivers:

   * Go to **Settings → Additional Drivers** (Ubuntu-based systems).

---

## 🛡️ Step 7: Optional (Dual Boot Instead of Replacing)

If you still want to **keep Windows** and use both OSes, here is the option for you:

* In Step 4, choose **“Install alongside Windows Boot Manager”** instead of “Erase disk.”
* Linux will automatically create a dual boot menu.

## The Unsolicited