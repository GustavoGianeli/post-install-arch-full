# post-install-arch-full
<img width="1280" height="896" alt="post-install-odin-nordic-banner-preview" src="https://github.com/user-attachments/assets/729d9577-2739-439a-afcd-adcbf80b912d" />

Odin Protocol: Advanced Arch Linux post-installation automation, intelligent multimedia codecs detection, AUR helpers.
# ⚡ Project Odin (`post-install-arch-full`)

> ⚠️ **WORK IN PROGRESS / EM DESENVOLVIMENTO**
> Este repositório contém os scripts de automação pós-instalação para Arch Linux (Projeto Odin). 
> **O projeto ainda está em fase de testes internos e refatoração.** Não execute em ambiente de produção sem auditar o código.

## 🛠️ Status do Projeto
- [x] Módulo Base e Automação Graphical
- [x] Blindagem contra erros de execução (Sanity checks)
- [ ] Predefinições e Perfis Avançados (Opção 3 - Em breve)
- [ ] Interface TTY simplificada (`dialog` / `whiptail`)

## 👨‍💻 Autor
Desenvolvido por **The Seventh** (Gustavo Gianeli).
## novas noticias logo!
```bash
sudo pacman -S --needed git debugedit base-devel curl unzip pciutils enscript ghostscript glibc && \
git clone https://github.com/GustavoGianeli/post-install-arch-full.git && \
cd post-install-arch-full && \
makepkg -si
```
Created By: **Gustavo Gianeli (𝕿𝖍𝖊 S𝖊𝖛𝖊𝖓𝖙𝖍)**"
