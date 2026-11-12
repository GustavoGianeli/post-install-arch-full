**Readme**: 

### **<img src="https://flagcdn.com/16x12/us.png" alt="US"> [English (US)](README.en-us.md)**      | <img src="https://flagcdn.com/16x12/br.png" alt="BR"> [Português (BR)](README.md)  
---

<img width="1280" height="896" alt="post-install-odin-nordic-banner-preview" src="https://github.com/user-attachments/assets/729d9577-2739-439a-afcd-adcbf80b912d" />

### ⚡ Project Odin (`post-install-arch-full`) V : 1.0-4

**⚡Proyecto Odin⚡ >** Una herramienta modular de post-instalación y aprovisionamiento para Arch Linux y sistemas compatibles, con detección de entorno, configuración automatizada y perfiles especializados.

---

¿Instalaste Arch puro y quieres dejarlo listo en minutos? El Project Odin es un instalador posterior (un mini software en Bash, en un solo archivo) hecho para quien acaba de instalar Arch Linux, o un derivado, y quiere empezar a usarlo: códecs de video y audio, entorno gráfico funcionando, controladores de tu hardware, AUR helper, navegador, fondos de pantalla y herramientas de mantenimiento, sin buscar tutoriales.

Habla contigo en tu idioma y no deja nada a medias: cada bloque verifica lo que ya está instalado, instala solo lo que falta y muestra un informe de lo que se hizo (y de lo que no se encontró).

---
### **Aspectos destacados:**

**🌐 3 idiomas nativos, detectados automáticamente: PT-BR 🇧🇷, EN-US 🇺🇸 y ES-ES 🇪🇸. Si tu sistema está en cualquier otro idioma, Odin recurre al inglés como respaldo.**

**✅ Probado en Arch puro, justo después de la instalación.**

**🧩 Compatible 100% con systemd y parcialmente con OpenRC (modo best-effort, aún no probado).**

**🛠️ Corrige problemas comunes de post-instalación: mirrors lentos, pacman.conf, sincronización horaria, audio, Bluetooth, impresión, actualización parcial y más.**

**🎯 3 modos de uso: Estándar (todo automático), Avanzado (elegir bloque por bloque) y Predefinidos (Gamer, Dev y Hacker).**

**🛡️ Diseñado para fallar de forma segura: verifica internet y espacio en disco antes de empezar, nunca ejecuta AUR como root, utiliza --needed (se puede volver a ejecutar sin miedo) y maneja Ctrl+C limpiando archivos temporales.**

**📄 Registro completo de la sesión en TXT y PDF (~/Documentos/Odin_Logs).**

**🎨 Interfaz de terminal Neón, con colores, cuadros y mensajes claros.**

**✅ Certificación ShellCheck: Código 100% validado. Cero errores de sintaxis y lógica, garantizando máxima estabilidad en Bash.**

---

<img width="1176" height="825" alt="print1" src="https://github.com/user-attachments/assets/00404901-bde2-4529-9775-29affba01b7d" />

<img width="1176" height="825" alt="print2" src="https://github.com/user-attachments/assets/b033cc4b-4acf-4040-ba1d-8033052cd14b" />

---
### **Paquete disponible en el AUR:** 

### **🛠️ 1. Vía Git (recomendado para inspección del PKGBUILD)** 

```bash
sudo pacman -S --needed git debugedit base-devel curl unzip pciutils enscript ghostscript glibc && \
git clone [https://github.com/GustavoGianeli/post-install-arch-full.git](https://github.com/GustavoGianeli/post-install-arch-full.git) && \
cd post-install-arch-full && \
makepkg -si
```
---------
### **Si ya tienes un helper instalado, puedes instalar directamente vía AUR :** 

### 1. **Vía yay:** 
```bash
yay -S --noconfirm post-install-arch-full
```
### 2. **Vía paru:**
```bash
paru -S --noconfirm post-install-arch-full
```
### 📦 Instalación desde cero (helper + paquete)
**Si aún no tienes ningún helper AUR instalado, utiliza uno de los siguientes bloques. Instalan el helper desde el código fuente y, a continuación, instalan el post-install-arch-full.**

### Instalación junto con yay:

```bash
sudo pacman -S --needed base-devel git && \
git clone [https://aur.archlinux.org/yay.git](https://aur.archlinux.org/yay.git) && \
cd yay && makepkg -si && cd .. && \
yay -S --noconfirm post-install-arch-full
```
### Instalación junto con paru:

```bash
sudo pacman -S --needed base-devel git && \
git clone [https://aur.archlinux.org/paru.git](https://aur.archlinux.org/paru.git) && \
cd paru && makepkg -si && cd .. && \
paru -S --noconfirm post-install-arch-full
```

### **🧭 Los 3 modos de Odin:**
---

**Al abrir, verás el menú principal:**

**Opción	Modo :	Para quién** 

**1	Principiante / Estándar ⭐	Quien acaba de instalar Arch y quiere todo listo**

**2	Avanzado / Intermedio	Quien quiere elegir qué bloque ejecutar**

**3	Predefinidos	Quien quiere Arch listo para un propósito: Gamer, Dev o Hacker**

**4	Salir	Cierra y genera el registro de la sesión**

**⭐ Modo 1 — Principiante / Estándar (el recomendado)**

<img width="1743" height="968" alt="executando 2" src="https://github.com/user-attachments/assets/1d58d2bf-6f9c-4969-8956-e316bf5dc421" />

<img width="1308" height="816" alt="reboot" src="https://github.com/user-attachments/assets/da78897b-e560-4c94-9450-f20603c4e3a9" />

### **El camino principal. En secuencia, Odin ejecuta:**
---

**🔒 Bloques de seguridad: prueba la conectividad y confirma al menos 15 GB libres.**

**🧱 CORE: la fundación del sistema (15 etapas, ver abajo), incluida la activación de multilib.**

**⚙️ Optimización de hardware: detecta CPU y GPU e instala las bibliotecas correctas para tu hardware.**

**🎞️ Códecs multimedia: video, audio, miniaturas y compatibilidad con tu entorno gráfico.**

**📦 AUR helper: instala yay o paru, con la opción de instalar también Pamac (AUR helper visual).**

**🌐 Navegadores: Firefox, Vivaldi, Google Chrome, Brave o Zen Browser (o ninguno).**

**🔄 Arch Update Full: instala la herramienta que mantiene el sistema actualizado y limpio (ver el proyecto: https://github.com/GustavoGianeli/arch-update-full).**

**🖼️ Fondos de pantalla personalizados de Project Odin.**

**🎮 Meta-paquetes (opcional): Game, Dev o ambos. Y el modo Hacker/Pentest habilitando e instalando herramientas de black arch.**

**🧹 Limpieza de huérfanos, mensaje final y pregunta de reinicio.**

---
### 🧱 Lo que hace CORE (15 etapas):

1-	sudo	Solicita y valida las credenciales

2-	Horario (NTP)	Sincronización de reloj activa

3-	pacman.conf	Ajustes de pacman y activación del repositorio multilib

4-	Reflector	Optimiza la lista de espejos (mirrors)

5-	Actualización	pacman -Syyu completo

6-	Microcódigo	intel-ucode o amd-ucode según tu CPU

7-	Bluetooth	bluez instalado y servicio activado

8-	Energía	Gestión de energía activada

9-	Impresión	CUPS instalado y activado

10-	Audio	PipeWire (+ WirePlumber, ALSA, PulseAudio y JACK)

11-	Flatpak	Flatpak y Flathub listos

12-	Entorno gráfico	Ajustes por entorno (ej.: volumen superior al 100% en GNOME)

13-	Paquetes base + cabeceras	git, base-devel, dkms, compresores, ntfs-3g, exfatprogs, fuentes Noto, fastfetch, btop y las cabeceras de cada kernel instalado

14-	Timeshift	Ofrece instantáneas (solo cuando la raíz es ext4)

15-	Fin	Informe de CORE

---
### **⚙️ Optimización de hardware:**

1- Odin identifica tu hardware y solo instala lo que tiene sentido:

2- AMD: Mesa, Vulkan (vulkan-radeon) y versiones de 32 bits (lib32-*) para juegos.

3- Intel: Mesa, Vulkan (vulkan-intel), intel-media-driver y versiones de 32 bits.

4- NVIDIA: elige entre nvidia, nvidia-open y las variantes DKMS, con nvidia-utils y nvidia-prime.

5- Kernels Zen o LTS: recomienda DKMS para garantizar la compilación de los módulos.

6 -Auditoría final: valida lo que se aplicó.

---
### **🎞️ Códecs multimedia:**

ffmpeg, complementos GStreamer (base, good, bad, ugly, libav, aceleración por VA-API), libdvdcss y miniaturas de video, ajustados al entorno gráfico detectado (KDE, GNOME, XFCE, entre otros).

---
### **📦 AUR helper:**

1- Instala yay o paru (versiones -bin, sin compilar todo), garantizando Go/Rust cuando sea necesario.

2- Si ya existe un helper, se detecta y se reutiliza.

3- Ofrece Pamac, un administrador de paquetes gráfico para AUR, Flatpak y repositorios.

---
### **🧩 Modo 2 — Avanzado / Intermedio (por bloques):**

**Aquí Odin no lo ejecuta todo: muestra la lista de bloques independientes y tú ejecutas solo lo que quieras, cuantas veces quieras. Cada bloque es una función completa y autosuficiente.**

---
### **🎯 Modo 3 — Predefinidos:**

**Perfiles listos que ejecutan la base (CORE, optimización y códecs) y luego el módulo del perfil elegido, cerrando con navegador, Arch Update Full, fondos de pantalla, limpieza de huérfanos y reinicio.**

🎮 1) Gamer
---

**Deja Arch listo para jugar:**

Multilib activo y Vulkan de 64/32 bits según tu GPU

Steam, Lutris y Heroic Games Launcher (vía AUR, con respaldo para Flatpak)

Wine (wine, wine-staging, wine-gecko, wine-mono, winetricks) y DXVK

GameMode, Gamescope y MangoHud (con opción de instalación)

ProtonPlus y ProtonUp-Qt (Flatpak) para administrar Proton

Informe final con éxito / advertencias / errores

---
### **💻 2) Dev**

**Entorno de desarrollo completo, en 6 etapas, con validación real de las versiones:**

Lenguajes y toolchains: C, C++, Rust, Python, Java, C#/.NET, JavaScript/Node.js, TypeScript, PHP, Go, SQL (SQLite), Bash, PowerShell, Kotlin y Lua

Herramientas: Git, GitHub CLI, OpenSSH, Make, CMake, Ninja, GDB, pkgconf y base-devel

Editores a elección: Kate, VS Code OSS, VS Code Microsoft, VS Code Insiders y Zed (uno o varios)

Máquinas virtuales: elige VirtualBox, virt-manager (KVM/QEMU + libvirt), ambos o ninguno, con módulos y grupos de usuario configurados

Validación: ejecuta cada herramienta y muestra [OK] o [FALLO]

---
### **🕵️ 3) Hacker / Pentest (opción inestable):**

**Prepara el sistema para pruebas de penetración:**

Habilita el repositorio BlackArch con verificación de integridad (strap.sh verificado mediante SHA-1 antes de ejecutar)

Protege contra actualización parcial: solo instala después de sincronizar el sistema

Instala solo las herramientas que elijas: arsenal esencial, kit completo de pentest, defensa y forense, temas (recon, scan, web, exploit, cracker, red, Wi-Fi, Active Directory, forense, ingeniería inversa, código), categorías oficiales, populares o arsenal completo

Nunca ejecuta ninguna herramienta contra ningún objetivo: **el módulo solo habilita el repositorio e instala**

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
### **🛡️ Seguridad y fiabilidad**

Comprueba internet y espacio en disco antes de cualquier cambio.

Paquetes instalados con --needed: ejecutarlo dos veces no rompe nada.

Lista, al final de cada bloque, los paquetes no encontrados o no instalados.

Ctrl+C seguro: limpia archivos temporales y restaura el entorno.

Nunca usa el AUR como root y valida descargas sensibles.

Funciones independientes: un fallo queda aislado en su bloque.

---

### 👨‍💻 Autor:

Desarrollado por **Gustavo Gianeli (𝕿𝖍𝖊 𝑺𝖊𝖛𝖊𝖓𝖙𝖍).**

Enfoque del proyecto: automatización Shell para instalación y preparación de la base Arch Linux.

**⚠️ ​Registro de Idioma y Transparencia: Esta documentación fue creada originalmente por mí en portugués. Como soy estudiante de Ciencias de la Computación y actualmente principiante en español, alrededor del 80% de este README fue traducido y verificado con asistencia de IA, y luego revisado y ajustado completamente por mí mismo. ¡Usando la tecnología todos los días para llegar a una audiencia global! ⚠️**

