pkgname=fastfetch
pkgver=2.70.0
pkgrel=1
pkgdesc='Fastfetch is a neofetch-like tool for fetching system information and displaying them in a pretty way'
arch=('x86_64')
url='https://github.com/fastfetch-cli/fastfetch'
license=('MIT')
depends=('glibc')
makedepends=('cmake')
source=("https://codeload.github.com/${pkgname}-cli/${pkgname}/tar.gz/refs/tags/${pkgver}")
sha256sums=('8aa01bd3faff2be1d94f231d76489ce6d9f781f51f6e93eafe82359d6d8669af')

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
