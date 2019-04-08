# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=tre-screen-setup
pkgver=1.6.0
pkgrel=1
pkgdesc="generate an xrendr and xinput command stream based on the contents of a station message"
arch=('any')
url=""
license=('MIT')
groups=()
depends=(
  'nodejs'
  'xdotool'
  'wmctrl'
  'compiz-user-service'
)
makedepends=('npm')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
source=(
  'tre-screen-setup@.service'
)

sha256sums=('7045d9a04f6dd49b56a82d5a8e56f52156c0b01bbbf1d6e51f1a0ed397a6db7d')

pkgver () {
  npm view ${pkgname}@latest version
}

package () {
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" ${pkgname}@${pkgver}

  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/user" 'tre-screen-setup@.service'
}
