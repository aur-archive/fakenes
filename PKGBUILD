# Maintainer: eldruz <eldruz at outlook dot com>
# Contributor: carstene1ns <url/mail: arch carsten-teibes de>
# Contributor: jsteel <jsteel at vorx dot com>
# Contributor: Christoph Zeiler <rabyte*gmail>

pkgname=fakenes
pkgver=0.5.9_beta3
pkgrel=10
pkgdesc="A NES (Nintendo Famicom) emulator"
arch=('i686' 'x86_64')
url="http://fakenes.sourceforge.net"
license=('ZLIB')
depends=('hawknl' 'openal' 'allegro4' 'glu')
makedepends=('mesa')
source=("http://downloads.sourceforge.net/$pkgname/$pkgname-0.5.9-beta3.tar.gz"
        "$pkgname.xpm"
        "$pkgname.desktop"
        "gcc-4.2.patch"
        "libraries.patch")
sha256sums=('c4477b19ee2b59cac9c122aa854b11e90c1f0598bfde5454dd81fd4bf431d008'
            'd54ca5baa74d793d8966126009bd75655d0d51ec4b7c7f064e816c858f3ca2a5'
            'dc1395d3d4a56be44608035255c251e5d7e20190e551133bb2b5082ed2109eb9'
            '2a954c2e35a3ad31d9e77b2d0a7f6de67671a131a878f49cdda122ceb80cf187'
            'e6ab6ad7a5b6439d7db5ac7a073576f12cbe13a0547cdd7a15fd69b8588afd56')
prepare() {
  cd $pkgname-${pkgver//_/-}
  patch -Np0 < ../gcc-4.2.patch
  patch -Np1 < ../libraries.patch
}
build() {
  cd $pkgname-${pkgver//_/-}
  make CFLAGS="${CFLAGS}"
}
package() {
  cd $pkgname-${pkgver//_/-}
  install -Dm755 $pkgname "$pkgdir"/usr/bin/$pkgname
  install -Dm644 ../$pkgname.xpm "$pkgdir"/usr/share/pixmaps/$pkgname.xpm
  install -Dm644 ../$pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
  install -Dm644 docs/LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
