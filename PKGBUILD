pkgname=fastfetch
pkgver=2.68.1
pkgrel=1
pkgdesc='Fastfetch is a neofetch-like tool for fetching system information and displaying them in a pretty way'
arch=('x86_64')
url='https://github.com/fastfetch-cli/fastfetch'
license=('MIT')
depends=('glibc')
makedepends=('cmake')
source=("https://codeload.github.com/${pkgname}-cli/${pkgname}/tar.gz/refs/tags/${pkgver}")
sha256sums=('c268cfcd230cc7ed5447fb34ed21bf4977315c7104356a39388b6ba784ad11b0')

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
