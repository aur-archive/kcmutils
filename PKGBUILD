# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kcmutils
pkgver=4.99.0
pkgrel=1
pkgdesc='Utilities for interacting with KCModules'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kcmutils'
license=('LGPL')
depends=('kxmlgui')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('65181f6aecacc907d1fce20977e9e0b8')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
