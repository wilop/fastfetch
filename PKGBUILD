pkgname=fastfetch
pkgver=2.56.1
pkgrel=1
pkgdesc='Fastfetch is a neofetch-like tool for fetching system information and displaying them in a pretty way'
arch=('x86_64')
url='https://github.com/fastfetch-cli/fastfetch'
license=('MIT')
depends=('glibc')
makedepends=('cmake')
source=("https://codeload.github.com/${pkgname}-cli/${pkgname}/tar.gz/refs/tags/${pkgver}")
sha256sums=('6ffd75c32b2a885fd8497867645ac837ed37d588c94e0df05408cdaa0c8fd2c7')

build() {
 cd "${pkgname}-${pkgver}"
 mkdir -p build
 cd build
 cmake .. -DBUILD_FLASHFETCH=OFF -DBUILD_TESTS=ON
 cmake --build .
}

check() {
 cd "${pkgname}-${pkgver}"
 ctest --test-dir build --output-on-failure
}

package() {
 cd "${pkgname}-${pkgver}"
 DESTDIR="${pkgdir}" cmake --install build
}
