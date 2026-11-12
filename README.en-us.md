**Readme**: 

### **<img src="https://flagcdn.com/16x12/es.png" alt="ES"> [Español (ES)](README.es-es.md)**      | <img src="https://flagcdn.com/16x12/br.png" alt="BR"> [Português (BR)](README.md)  
---


<img width="1280" height="896" alt="post-install-odin-nordic-banner-preview" src="https://github.com/user-attachments/assets/16258984-112a-47e3-b0d6-9917c70ddce1" />

### ⚡ Project Odin (`post-install-arch-full`) V : 1.0-4

**⚡Project Odin⚡ >** A modular post-install and provisioning tool for Arch Linux and compatible systems, with environment detection, automated setup, and specialized profiles.

---

Just installed a bare Arch and want it ready in minutes? Project Odin is a post-installer (a small Bash program in a single file) made for people who just installed Arch Linux, or a derivative, and want to start using it right away: video and audio codecs, a working graphical environment, drivers for your hardware, an AUR helper, a browser, wallpapers, and maintenance tools, without hunting for tutorials.

It talks to you in your language and never leaves anything half-done: each block checks what's already installed, installs only what's missing, and shows a report of what was done (and what wasn't found).

---
 ### **Highlights:**

**🌐 3 native languages, detected automatically: PT-BR 🇧🇷, EN-US 🇺🇸 and ES-ES 🇪🇸. If your system uses any other language, Odin falls back to English.**

**✅ Tested on a bare Arch, right after installation.**

**🧩 100% compatible with systemd and partially compatible with OpenRC (best-effort mode, not tested yet).**

**🛠️ Fixes common post-install problems: slow mirrors, pacman.conf, clock sync, audio, Bluetooth, printing, partial upgrades, and more.**

**🎯 3 modes of use: Standard (fully automatic), Advanced (pick block by block), and Pre-defined (Gamer, Dev, and Hacker).**

**🛡️ Built to fail safely: checks your internet and disk space before starting, never runs the AUR as root, uses --needed (safe to run again), and handles Ctrl+C by cleaning up temporary files.**

**📄 Full session log in TXT and PDF (~/Documentos/Odin_Logs).**

**🎨 Neon terminal interface, with colors, boxes, and clear messages.**

**✅ ShellCheck certification: 100% validated code. Zero syntax and logic errors, ensuring maximum stability in Bash.**

---

<img width="1176" height="825" alt="print1" src="https://github.com/user-attachments/assets/d446bcf7-da87-4f92-94f3-51d6aa4b02be" />

<img width="1176" height="825" alt="print2" src="https://github.com/user-attachments/assets/d49d1194-4cf7-4b96-94c6-6268269a743e" />

---
### **Package available on the AUR:** 

### **🛠️ 1. Via Git (recommended if you want to inspect the PKGBUILD)** 

```bash
sudo pacman -S --needed git debugedit base-devel curl unzip pciutils enscript ghostscript glibc && \
git clone https://github.com/GustavoGianeli/post-install-arch-full.git && \
cd post-install-arch-full && \
makepkg -si
```
---------
### **If you already have a helper installed, you can install straight from the AUR:** 

### 1. **Via yay:** 
```bash
yay -S --noconfirm post-install-arch-full
```
### 2. **Via paru:**
```bash
paru -S --noconfirm post-install-arch-full
```
### 📦 Installing from scratch (helper + package)
**If you don't have an AUR helper installed yet, use one of the blocks below. They install the helper from source and then install post-install-arch-full right after.**

### Installing together with yay:

```bash
sudo pacman -S --needed base-devel git && \
git clone https://aur.archlinux.org/yay.git && \
cd yay && makepkg -si && cd .. && \
yay -S --noconfirm post-install-arch-full
```
### Installing together with paru:

```bash
sudo pacman -S --needed base-devel git && \
git clone https://aur.archlinux.org/paru.git && \
cd paru && makepkg -si && cd .. && \
paru -S --noconfirm post-install-arch-full
```

### **🧭 Odin's 3 modes:**
---

**When you open it, you'll see the main menu:**

**Option	Mode :	Who it's for** 

**1	Beginner / Standard ⭐	Anyone who just installed Arch and wants everything ready**

**2	Advanced / Intermediate	Anyone who wants to choose which block to run**

**3	Pre-defined	Anyone who wants Arch ready for a specific purpose: Gamer, Dev, or Hacker**

**4	Exit	Closes the program and generates the session log**

**⭐ Mode 1 — Beginner / Standard (the recommended one)**

<img width="1743" height="968" alt="executando 2" src="https://github.com/user-attachments/assets/1d58d2bf-6f9c-4969-8956-e316bf5dc421" />

<img width="1308" height="816" alt="reboot" src="https://github.com/user-attachments/assets/da78897b-e560-4c94-9450-f20603c4e3a9" />

---
### **The main path. In sequence, Odin executes:**
---

**🔒 Security blocks: tests connectivity and confirms at least 15 GB free.**

**🧱 CORE: the system foundation (15 steps, see below), including multilib activation.**

**⚙️ Hardware optimization: detects CPU and GPU and installs the correct libraries for your hardware.**

**🎞️ Multimedia codecs: video, audio, thumbnails, and support for your desktop environment.**

**📦 AUR helper: installs yay or paru, with the option to also install Pamac (visual AUR helper).**

**🌐 Browsers: Firefox, Vivaldi, Google Chrome, Brave, or Zen Browser (or none).**

**🔄 Arch Update Full: installs the tool that keeps the system updated and clean (see project: https://github.com/GustavoGianeli/arch-update-full).**

**🖼️ Custom Project Odin wallpapers.**

**🎮 Meta-packages (optional): Game, Dev, or both. And Hacker/Pentest mode enabling and installing black arch tools.**

**🧹 Orphan cleanup, final message, and reboot prompt.**

---
### 🧱 What CORE does (15 steps):

1-	sudo	Requests and validates credentials

2-	Time (NTP)	Active clock synchronization

3-	pacman.conf	Pacman adjustments and multilib repository activation

4-	Reflector	Optimizes the mirror list

5-	Update	Complete pacman -Syyu

6-	Microcode	intel-ucode or amd-ucode according to your CPU

7-	Bluetooth	bluez installed and service enabled

8-	Power	Power management enabled

9-	Printing	CUPS installed and enabled

10-	Audio	PipeWire (+ WirePlumber, ALSA, PulseAudio, and JACK)

11-	Flatpak	Flatpak and Flathub ready

12-	Desktop environment	Environment tweaks (e.g., volume above 100% in GNOME)

13-	Base packages + headers	git, base-devel, dkms, compressors, ntfs-3g, exfatprogs, Noto fonts, fastfetch, btop, and headers for each installed kernel

14-	Timeshift	Offers snapshots (only when root is ext4)

15-	End	CORE report

---
### **⚙️ Hardware optimization:**

1- Odin identifies your hardware and installs only what makes sense:

2- AMD: Mesa, Vulkan (vulkan-radeon), and 32-bit versions (lib32-*) for gaming.

3- Intel: Mesa, Vulkan (vulkan-intel), intel-media-driver, and 32-bit versions.

4- NVIDIA: chooses between nvidia, nvidia-open, and DKMS variants, with nvidia-utils and nvidia-prime.

5- Zen or LTS Kernels: recommends DKMS to ensure module compilation.

6 -Final audit: validates what was applied.

---
### **🎞️ Multimedia codecs:**

ffmpeg, GStreamer plugins (base, good, bad, ugly, libav, VA-API acceleration), libdvdcss, and video thumbnails, adjusted to the detected desktop environment (KDE, GNOME, XFCE, among others).

---
### **📦 AUR helper:**

1- Installs yay or paru (-bin versions, without compiling everything), ensuring Go/Rust when necessary.

2- If a helper already exists, it is detected and reused.

3- Offers Pamac, a graphical package manager for AUR, Flatpak, and repositories.

---
### **🧩 Mode 2 — Advanced / Intermediate (by blocks):**

**Here Odin does not run everything: it displays the list of independent blocks and you execute only what you want, as many times as you want. Each block is a complete and self-sufficient function.**

---
### **🎯 Mode 3 — Pre-defined:**

**Ready-made profiles that run the base (CORE, optimization, and codecs) and then the chosen profile's module, closing with browser, Arch Update Full, wallpapers, orphan cleanup, and reboot.**

🎮 1) Gamer
---

**Gets Arch ready for gaming:**

Active multilib and 64/32-bit Vulkan according to your GPU

Steam, Lutris, and Heroic Games Launcher (via AUR, with Flatpak fallback)

Wine (wine, wine-staging, wine-gecko, wine-mono, winetricks) and DXVK

GameMode, Gamescope, and MangoHud (with installation option)

ProtonPlus and ProtonUp-Qt (Flatpak) to manage Proton

Final report with success / warnings / errors

---
### **💻 2) Dev**

**Complete development environment in 6 steps, with real version validation:**

Languages and toolchains: C, C++, Rust, Python, Java, C#/.NET, JavaScript/Node.js, TypeScript, PHP, Go, SQL (SQLite), Bash, PowerShell, Kotlin, and Lua

Tools: Git, GitHub CLI, OpenSSH, Make, CMake, Ninja, GDB, pkgconf, and base-devel

Editors of choice: Kate, VS Code OSS, VS Code Microsoft, VS Code Insiders, and Zed (one or multiple)

Virtual machines: choose VirtualBox, virt-manager (KVM/QEMU + libvirt), both, or none, with configured modules and user groups

Validation: executes each tool and displays [OK] or [FAIL]

---
### **🕵️ 3) Hacker / Pentest (unstable option):**

**Prepares the system for penetration testing:**

Enables the BlackArch repository with integrity verification (strap.sh checked via SHA-1 before execution)

Protects against partial updates: only installs after full system synchronization

Installs only the tools you choose: essential arsenal, complete pentest kit, defense and forensics, themes (recon, scan, web, exploit, cracker, network, Wi-Fi, Active Directory, forensics, reverse engineering, code), official categories, popular tools, or complete arsenal

Never executes any tool against any target: **the module only enables the repository and installs**

---

<img width="1176" height="825" alt="print2" src="https://github.com/user-attachments/assets/b0ec5c17-991e-450a-bb56-3eb1a96a0dab" />

<img width="1146" height="829" alt="modo 2" src="https://github.com/user-attachments/assets/c2f81f6f-3054-43a4-9c1f-4f8d36c574dc" />

<img width="1308" height="816" alt="modos pre definidos" src="https://github.com/user-attachments/assets/e375b18a-da5c-40c1-bc3e-aa3b16b2dbe7" />

<img width="1308" height="816" alt="hacker mode" src="https://github.com/user-attachments/assets/3e3459f9-ec0f-409f-a181-937b2d8b5a46" />

<img width="1308" height="816" alt="repoblackarch" src="https://github.com/user-attachments/assets/c7f8422d-13ee-418c-845d-df4731462c76" />

<img width="1176" height="825" alt="kdejogo" src="https://github.com/user-attachments/assets/afdb0e5d-030a-4bcd-b252-dbb0af1b11a3" />

<img width="1176" height="825" alt="kde jogos 2" src="https://github.com/user-attachments/assets/ec7eb510-45fd-4324-ace9-bdd59f8679f7" />

<img width="1345" height="846" alt="cosmic dev" src="https://github.com/user-attachments/assets/b6de3360-7d44-42e2-b04a-1659a8205ed6" />

<img width="1308" height="816" alt="depois de instalado" src="https://github.com/user-attachments/assets/b21b6d51-2a4c-462e-b3f9-50a6349bde4e" />

<img width="1308" height="816" alt="wallpaper personalizados " src="https://github.com/user-attachments/assets/07fac3cb-d685-4ce7-829d-b343109007a0" />

<img width="1308" height="816" alt="reboot" src="https://github.com/user-attachments/assets/f6a26ae5-d3e4-4dd7-9447-5ed63fd724ac" />

---
### **🛡️ Security and reliability**

Checks internet connection and disk space before making any changes.

Packages installed with --needed: running twice won't break anything.

Lists, at the end of each block, packages that were not found or not installed.

Safe Ctrl+C: cleans temporary files and restores the environment.

Never uses AUR as root and validates sensitive downloads.

Independent functions: a failure remains isolated in its block.

---

### 👨‍💻 Author:

Developed by **Gustavo Gianeli (𝕿𝖍𝖊 𝑺𝖊𝖛𝖊𝖓𝖙𝖍).**

Project focus: Shell automation for installing and preparing the Arch Linux base.

**⚠️ ​Language & Transparency Log: This documentation was originally created by me in Portuguese. Since I am a Computer Science student and currently an English beginner, about 80% of this README was translated and verified with AI assistance, then fully reviewed and adjusted by myself. Using technology every day to reach a global audience !⚠️**
