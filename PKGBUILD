# Merged with official ABS kpeoplevcard PKGBUILD by João, 2021/02/18 (all respective contributors apply herein)
# Maintainer: João Figueiredo <jf.mundox@gmail.com>
# Contributor: Rihards Skuja <rhssk at posteo eu>

pkgname=kpeoplevcard-git
pkgver=0.1_r41.gb10c103
pkgrel=1
pkgdesc='Makes it possible to expose vcards to KPeople'
url='https://kde.org/'
license=(GPL)
arch=($CARCH)
depends=(kpeople-git kcontacts-git)
makedepends=(git extra-cmake-modules-git)
conflicts=(${pkgname%-git})
provides=(${pkgname%-git})
source=("git+https://github.com/KDE/${pkgname%-git}.git")
sha256sums=('SKIP')

pkgver() {
      cd ${pkgname%-git}
        _ver="$(git describe | sed 's/^v//;s/-.*//')"
          echo "${_ver}_r$(git rev-list --count HEAD).g$(git rev-parse --short HEAD)"
}

build() {
      cmake -B build -S ${pkgname%-git} \
          -DBUILD_TESTING=OFF
            cmake --build build
}

package() {
      DESTDIR="$pkgdir" cmake --install build
}
