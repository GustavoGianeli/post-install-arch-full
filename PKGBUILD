# Maintainer: The_Seventh <gustavo.gianeli13@gmail.com>
pkgname=post-install-arch-full
pkgver=0.1
pkgrel=1
pkgdesc="Advanced Arch Linux post-installation automation, intelligent multimedia codecs detection, and system setup."
arch=('any')
url="https://github.com/GustavoGianeli/post-install-arch-full"
license=('GPL3')
depends=('bash' 'pacman')


# --- ADICIONADO O ÍCONE NO SOURCE // The icon has been added to the source. ---
source=(
  "post-install-arch-full"
  "post-install-arch-full.desktop"	
  "iconeodin.png"
  "LICENSE"
)

# Use 'updpkgsums' para preencher isso automaticamente // Use 'updpkgsums' to automatically fill this in.

sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            )

package() {

  # 1. Instala o script executável
  install -Dm755 "${srcdir}/post-install-arch-full" "${pkgdir}/usr/bin/post-install-arch-full"
  
  # 2. Instala o atalho no menu
  install -Dm644 "${srcdir}/post-install-arch-full.desktop" "${pkgdir}/usr/share/applications/post-install-arch-full.desktop"

  # 3. Ícones globais e do sistema
  install -Dm644 "${srcdir}/iconeodin.png" "${pkgdir}/usr/share/pixmaps/iconeodin.png"
  
  # 4. Instala a licença GPLv3 obrigatória
  install -Dm644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  
}

