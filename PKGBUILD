# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=tre-screen-setup
pkgver=1.6.0
pkgrel=2
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
  'restart-puppeteer'
)

sha256sums=('34d5df7420ace8c1d6b7de8767dcb340f433824b0957cd48f9f90f4de1a59b34'
            '1026028970aad44d0879a93f615a54b688fa601208f2179781aceca7232bae0e')

pkgver () {
  npm view ${pkgname}@latest version
}

package () {
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" ${pkgname}@${pkgver}

  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/user" tre-screen-setup@.service
  install -Dm 755 -t "${pkgdir}/usr/bin" restart-puppeteer
}
