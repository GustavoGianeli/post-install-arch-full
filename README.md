<img src="https://flagcdn.com/16x12/us.png" alt="US"> [English (US)](README.en-us.md) 
---

<img width="1280" height="896" alt="post-install-odin-nordic-banner-preview" src="https://github.com/user-attachments/assets/729d9577-2739-439a-afcd-adcbf80b912d" />

### ⚡ Project Odin (`post-install-arch-full`) V : 1.0-4

**⚡Projeto Odin⚡ >** Uma ferramenta modular de pós-instalação e provisionamento para Arch Linux e sistemas compatíveis, com detecção de ambiente, configuração automatizada e perfis especializados.

---

Instalou o Arch puro e quer deixá-lo pronto em minutos? O Project Odin é um pós-instalador (um mini software em Bash, em um único arquivo) feito para quem acabou de instalar o Arch Linux, ou um derivado, e quer sair usando: codecs de vídeo e áudio, ambiente gráfico funcionando, drivers do seu hardware, AUR helper, navegador, wallpapers e ferramentas de manutenção, sem caçar tutorial.

Ele conversa com você no seu idioma e não deixa nada pela metade: cada bloco verifica o que já está instalado, instala só o que falta e mostra um relatório do que foi feito (e do que não foi encontrado).

---
 ### **Destaques:**

**🌐 3 idiomas nativos, detectados automaticamente: PT-BR 🇧🇷, EN-US 🇺🇸 e ES-ES 🇪🇸. Se o seu sistema estiver em qualquer outro idioma, o Odin entra em fallback para inglês.**

**✅ Testado em Arch puro, logo após a instalação.**

**🧩 Compatível 100% com systemd e parcialmente com OpenRC (modo best-effort, ainda não testado).**

**🛠️ Corrige problemas comuns pós-instalação: mirrors lentos, pacman.conf, sincronização de horário, áudio, Bluetooth, impressão, atualização parcial e mais.**

**🎯 3 modos de uso: Padrão (tudo automático), Avançado (escolha bloco a bloco) e Pré-definidos (Gamer, Dev e Hacker).**

**🛡️ Pensado para falhar com segurança: checa internet e espaço em disco antes de começar, nunca roda o AUR como root, usa --needed (pode rodar de novo sem medo) e trata Ctrl+C limpando arquivos temporários.**

**📄 Log completo da sessão em TXT e PDF (~/Documentos/Odin_Logs).**

**🎨 Interface de terminal Neon, com cores, caixas e mensagens claras.**

**✅ Certificação ShellCheck: Código 100% validado. Zero erros de sintaxe e lógica, garantindo estabilidade máxima no Bash.**

---

<img width="1176" height="825" alt="print1" src="https://github.com/user-attachments/assets/00404901-bde2-4529-9775-29affba01b7d" />
<img width="1176" height="825" alt="print2" src="https://github.com/user-attachments/assets/b033cc4b-4acf-4040-ba1d-8033052cd14b" />


### **Pacote disponível no AUR:** 

### **🛠️ 1. Via Git (recomendado para inspeção do PKGBUILD)** 

```bash
sudo pacman -S --needed git debugedit base-devel curl unzip pciutils enscript ghostscript glibc && \
git clone https://github.com/GustavoGianeli/post-install-arch-full.git && \
cd post-install-arch-full && \
makepkg -si
```
---------
### **Se você já tem um helper instalado, pode instalar direto via AUR :** 

### 1. **Via yay:** 
```bash
yay -S --noconfirm post-install-arch-full
```
### 2. **Via paru:**
```bash
paru -S --noconfirm post-install-arch-full
```
### 📦 Instalação do zero (helper + pacote)
**Se você ainda não tem nenhum helper AUR instalado, use um dos blocos abaixo. Eles instalam o helper a partir do código-fonte e, na sequência, já instalam o post-install-arch-full.**

### Instalação junto com yay:

```bash
sudo pacman -S --needed base-devel git && \
git clone https://aur.archlinux.org/yay.git && \
cd yay && makepkg -si && cd .. && \
yay -S --noconfirm post-install-arch-full
```
### Instalação junto com paru:

```bash
sudo pacman -S --needed base-devel git && \
git clone https://aur.archlinux.org/paru.git && \
cd paru && makepkg -si && cd .. && \
paru -S --noconfirm post-install-arch-full
```

### **🧭 Os 3 modos do Odin:**
---

**Ao abrir, você vê o menu principal:**

**Opção	Modo :	Para quem** 

**1	Iniciante / Padrão ⭐	Quem acabou de instalar o Arch e quer tudo pronto**

**2	Avançado / Intermediário	Quem quer escolher qual bloco executar**

**3	Pré-definidos	Quem quer o Arch pronto para um propósito: Gamer, Dev ou Hacker**

**4	Sair	Encerra e gera o log da sessão**

**⭐ Modo 1 — Iniciante / Padrão (o recomendado)**

<img width="1743" height="968" alt="executando 2" src="https://github.com/user-attachments/assets/1d58d2bf-6f9c-4969-8956-e316bf5dc421" />
<img width="1308" height="816" alt="reboot" src="https://github.com/user-attachments/assets/da78897b-e560-4c94-9450-f20603c4e3a9" />


### **O caminho principal. Em sequência, o Odin executa:**
---

**🔒 Blocos de segurança: testa a conectividade e confirma pelo menos 15 GB livres.**

**🧱 CORE: a fundação do sistema (15 etapas, veja abaixo), incluindo a ativação do multilib.**

**⚙️ Otimização de hardware: detecta CPU e GPU e instala as bibliotecas certas para o seu hardware.**

**🎞️ Codecs multimídia: vídeo, áudio, miniaturas e suporte ao seu ambiente gráfico.**

**📦 AUR helper: instala yay ou paru, com a opção de instalar também o Pamac (AUR helper visual).**

**🌐 Navegadores: Firefox, Vivaldi, Google Chrome, Brave ou Zen Browser (ou nenhum).**

**🔄 Arch Update Full: instala a ferramenta que mantém o sistema atualizado e limpo (veja o projeto: https://github.com/GustavoGianeli/arch-update-full).**

**🖼️ Wallpapers personalizados do Projeto Odin.**

**🎮 Meta-pacotes (opcional): Game, Dev ou ambos. E o modo Hacker/Pentest habilitando e instalando ferramentas do black arch.**

**🧹 Limpeza de órfãos, mensagem final e pergunta de reinício.**

---
### 🧱 O que o CORE faz (15 etapas):

1-	sudo	Solicita e valida as credenciais

2-	Horário (NTP)	Sincronização de relógio ativa

3-	pacman.conf	Ajustes do pacman e ativação do repositório multilib

4-	Reflector	Otimiza a lista de espelhos (mirrors)

5-	Atualização	pacman -Syyu completo

6-	Microcódigo	intel-ucode ou amd-ucode conforme sua CPU

7-	Bluetooth	bluez instalado e serviço ativado

8-	Energia	Gerenciamento de energia ativado

9-	Impressão	CUPS instalado e ativado

10-	Áudio	PipeWire (+ WirePlumber, ALSA, PulseAudio e JACK)

11-	Flatpak	Flatpak e Flathub prontos

12-	Ambiente gráfico	Ajustes por ambiente (ex.: volume acima de 100% no GNOME)

13-	Pacotes base + headers	git, base-devel, dkms, compactadores, ntfs-3g, exfatprogs, fontes Noto, fastfetch, btop e os headers de cada kernel instalado

14-	Timeshift	Oferece snapshots (somente quando a raiz é ext4)

15-	Fim	Relatório do CORE

---
### **⚙️ Otimização de hardware:**

1- O Odin identifica seu hardware e instala só o que faz sentido:

2- AMD: Mesa, Vulkan (vulkan-radeon) e versões 32 bits (lib32-*) para jogos.

3- Intel: Mesa, Vulkan (vulkan-intel), intel-media-driver e versões 32 bits.

4- NVIDIA: escolhe entre nvidia, nvidia-open e as variantes DKMS, com nvidia-utils e nvidia-prime.

5- Kernels Zen ou LTS: recomenda DKMS para garantir a compilação dos módulos.

6 -Auditoria final: valida o que foi aplicado.

---
### **🎞️ Codecs multimídia:**

ffmpeg, plugins GStreamer (base, good, bad, ugly, libav, aceleração por VA-API), libdvdcss e miniaturas de vídeo, ajustados ao ambiente gráfico detectado (KDE, GNOME, XFCE, entre outros).

---
### **📦 AUR helper:**

1- Instala yay ou paru (versões -bin, sem compilar tudo), garantindo Go/Rust quando necessário.

2- Se já existir um helper, ele é detectado e reaproveitado.

3- Oferece o Pamac, um gerenciador de pacotes gráfico para AUR, Flatpak e repositórios.

---
### **🧩 Modo 2 — Avançado / Intermediário (por blocos):**

**Aqui o Odin não roda tudo: ele mostra a lista de blocos independentes e você executa só o que quiser, quantas vezes quiser. Cada bloco é uma função completa e autossuficiente.**

---
### **🎯 Modo 3 — Pré-definidos:**

**Perfis prontos que rodam a base (CORE, otimização e codecs) e depois o módulo do perfil escolhido, fechando com navegador, Arch Update Full, wallpapers, limpeza de órfãos e reinício.**

🎮 1) Gamer
---

**Deixa o Arch pronto para jogar:**

Multilib ativo e Vulkan 64/32 bits de acordo com a sua GPU

Steam, Lutris e Heroic Games Launcher (via AUR, com fallback para Flatpak)

Wine (wine, wine-staging, wine-gecko, wine-mono, winetricks) e DXVK

GameMode, Gamescope e MangoHud (com opção de instalar)

ProtonPlus e ProtonUp-Qt (Flatpak) para gerenciar o Proton

Relatório final com sucesso / avisos / erros

---
### **💻 2) Dev**

**Ambiente de desenvolvimento completo, em 6 etapas, com validação real das versões:**

Linguagens e toolchains: C, C++, Rust, Python, Java, C#/.NET, JavaScript/Node.js, TypeScript, PHP, Go, SQL (SQLite), Bash, PowerShell, Kotlin e Lua

Ferramentas: Git, GitHub CLI, OpenSSH, Make, CMake, Ninja, GDB, pkgconf e base-devel

Editores à escolha: Kate, VS Code OSS, VS Code Microsoft, VS Code Insiders e Zed (um ou vários)

Máquinas virtuais: escolha VirtualBox, virt-manager (KVM/QEMU + libvirt), ambos ou nenhum, com módulos e grupos de usuário configurados

Validação: executa cada ferramenta e mostra [OK] ou [FALHA]

---
### **🕵️ 3) Hacker / Pentest (opção instável):**

**Prepara o sistema para testes de invasão:**

Habilita o repositório BlackArch com verificação de integridade (strap.sh conferido por SHA-1 antes de executar)

Protege contra atualização parcial: só instala depois de sincronizar o sistema

Instala só as ferramentas que você escolher: arsenal essencial, kit completo de pentest, defesa e forense, temas (recon, scan, web, exploit, cracker, rede, Wi-Fi, Active Directory, forense, engenharia reversa, código), categorias oficiais, populares ou arsenal completo

Nunca executa nenhuma ferramenta contra alvo algum: **o módulo só habilita o repositório e instala**

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
### **🛡️ Segurança e confiabilidade**

Verifica internet e espaço em disco antes de qualquer alteração.

Pacotes instalados com --needed: rodar duas vezes não quebra nada.

Lista, no final de cada bloco, os pacotes não encontrados ou não instalados.

Ctrl+C seguro: limpa temporários e restaura o ambiente.

Nunca usa o AUR como root e valida downloads sensíveis.

Funções independentes: uma falha fica isolada no seu bloco.

---

### 👨‍💻 Autor:

Desenvolvido por **Gustavo Gianeli (𝕿𝖍𝖊 𝑺𝖊𝖛𝖊𝖓𝖙𝖍).**

Foco do projeto: automação Shell para instalação e preparação da base Arch Linux.


