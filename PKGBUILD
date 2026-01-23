pkgname=fastfetch
pkgver=2.58.0
pkgrel=1
pkgdesc='Fastfetch is a neofetch-like tool for fetching system information and displaying them in a pretty way'
arch=('x86_64')
url='https://github.com/fastfetch-cli/fastfetch'
license=('MIT')
depends=('glibc')
makedepends=('cmake')
source=("https://codeload.github.com/${pkgname}-cli/${pkgname}/tar.gz/refs/tags/${pkgver}")
sha256sums=('95c6bb522d455ed0bd35cc0f7f3a44a70663c0e81d03fe9bfe6ffa5ea19c2b1d')

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
