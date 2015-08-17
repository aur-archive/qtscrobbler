# Maintainer: Simon Legner <simon dot legner at gmail dot com>
# Contributor: Alucryd <alucryd at gmail dot com>

pkgname=qtscrobbler
pkgver=0.11
pkgrel=3
pkgdesc="A tool for submitting .scrobbler.log from portable players to Last.fm"
arch=('i686' 'x86_64')
url="http://qtscrob.sourceforge.net/"
license=('GPL')
depends=('libmtp' 'qt4')
makedepends=('ccache')
install=${pkgname}.install
source=("http://downloads.sourceforge.net/project/qtscrob/qtscrob/${pkgver}/qtscrob-${pkgver}.tar.bz2")
sha256sums=('01c8e48f616ed09504833d27d92fd62f455bd645ea2d1cc2a5f4c287d641daba')

build() {
  cd "$srcdir"/qtscrob-${pkgver}/src
  qmake-qt4
  make
}

package() {
  cd "$srcdir"/qtscrob-${pkgver}/src
  install -dm 755 "${pkgdir}"/usr/{bin,share/{applications,icons/hicolor}}
  install -m 755 qt/qtscrob "${pkgdir}"/usr/bin/qtscrob
  install -m 644 qt/qtscrob.desktop "${pkgdir}"/usr/share/applications/qtscrob.desktop
  for s in 16 32 48 64 128 256 512 ; do
    install -dm 755 "${pkgdir}"/usr/share/icons/hicolor/${s}x${s}/apps
    install -m 644 qt/resources/icons/${s}x${s}/qtscrob.png "${pkgdir}"/usr/share/icons/hicolor/${s}x${s}/apps/qtscrob.png
  done
}

# vim:set ts=2 sw=2 et:
