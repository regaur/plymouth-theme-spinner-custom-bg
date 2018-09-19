# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname='plymouth-theme-spinner-custom-bg'
pkgver=1.0
pkgrel=1
pkgdesc="Like the spinner theme, but using /usr/share/backgrounds/loading.png"
packager='Jan Boelsche'
arch=('any')
license=('GPL')
groups=()
depends=('plymouth' 'sed' 'background')
install=${pkgname}.install

source=(
  'spinner-theme.tar'
  'spinner-custom-bg.plymouth'
)

sha256sums=('82ff5541f6ceab006ba689ece2431a5de11f62309099640d848b440b89df0047'
            'a6e2d85cd2704f2154051087d9f93e633f6bb1cbd33c22220088d6b4430af393')

prepare () {
  dest='spinner-custom-bg'
  cp -r spinner "${dest}"
  rm ${dest}/background-tile.png
  rm ${dest}/spinner.plymouth
  cp spinner-custom-bg.plymouth "${dest}"
  ln -s /usr/share/backgrounds/loading.png "${dest}/background-tile.png"
}

package () {
  install -d "${pkgdir}/usr/share/plymouth/themes"
  cp -r spinner-custom-bg "${pkgdir}/usr/share/plymouth/themes" 
}
