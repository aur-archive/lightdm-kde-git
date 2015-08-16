# Maintainer: Xiao-Long Chen <chenxiaolong@cxl.epac.to>

pkgname=lightdm-kde-git
pkgver=375.14849e4
pkgrel=1
pkgdesc="LightDM Greeter for KDE"
arch=('i686' 'x86_64')
url="https://projects.kde.org/projects/playground/base/lightdm"
license=('GPL')
depends=('liblightdm-qt4' 'lightdm' 'qt4' 'openssl' 'perl' 'phonon' 'kdelibs')
makedepends=('git' 'cmake')
provides=('lightdm-kde')
conflicts=('lightdm-kde')
source=('lightdm-kde::git+git://anongit.kde.org/lightdm')
sha512sums=('SKIP')

pkgver() {
  cd lightdm-kde
  echo $(git rev-list --count master).$(git rev-parse --short master)
}

build() {
  cd "${srcdir}/lightdm-kde"

  mkdir build/ && cd build/
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake-qt4
  make
}

package() {
  cd "${srcdir}/lightdm-kde/build"
  make DESTDIR="${pkgdir}/" install
}

# vim:set ts=2 sw=2 et:
