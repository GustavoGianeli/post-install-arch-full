# # ⚡ Project Odin (`post-install-arch-full`)
<img width="1280" height="896" alt="post-install-odin-nordic-banner-preview" src="https://github.com/user-attachments/assets/729d9577-2739-439a-afcd-adcbf80b912d" />

Odin Protocol: Advanced Arch Linux post-installation automation, intelligent multimedia codecs detection, AUR helpers.

> ⚠️ **WORK IN PROGRESS / EM DESENVOLVIMENTO**
> Este repositório contém os scripts de automação pós-instalação para Arch Linux (Projeto Odin). 
> **O projeto ainda está em fase de testes internos e refatoração.** Não execute em ambiente de produção sem auditar o código.

## 🛠️ Status do Projeto
- [x] Módulo Base e Automação Graphical
- [x] Blindagem contra erros de execução (Sanity checks)
- [x] Predefinições e Perfis Avançados (Opção 3 - Em breve)
- [ ] Interface TTY simplificada (`dialog` / `whiptail`)
## novas noticias logo!

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

### Intalação junto com yay:

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
## 👨‍💻 Autor
Desenvolvido por **The Seventh** (Gustavo Gianeli).
