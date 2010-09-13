# Maintainer: schuay <jakob.gruber@gmail.com>
# Maintainer: Mike Sampson <mike at sambodata dot com>
# Contributor: Adrian Stratulat <adrian.stratulat at inboxcom>
# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: KillaB <xGenoBlast@gmail.com>
# Contributor: Callan Barrett <wizzomafizzo@gmail.com>
# Contributor: Christian Schmidt <xmucknertx@googlemail.com>
# Contributor: Sebastian Sareyko <public@nooms.de>

pkgname=angband
pkgver=3.1.2v2
pkgrel=1
pkgdesc="A roguelike dungeon exploration game based on the writings of JRR Tolkien"
arch=('i686' 'x86_64')
url="http://rephial.org/"
license=('GPL2' 'custom')
depends=('sdl_image' 'sdl_ttf' 'sdl_mixer' 'ncurses' 'libglade')
source=("http://rephial.org/downloads/${pkgver:0:3}/${pkgname}-${pkgver}-src.tar.gz")
md5sums=('e6d8e441fb8df1534f6aa0d047685c57')

build() {

  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure \
    --prefix=/usr \
    --bindir=/usr/bin \
    --sysconfdir=/usr/share/angband \
    --with-configpath=/usr/share/angband \
    --with-libpath=/usr/share/angband \
    --enable-gtk \
    --enable-sdl \
    --enable-sdl-mixer

  make

}

package() {

  cd "${srcdir}/${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install

  rm -f "${pkgdir}/usr/share/angband/*/delete.me"
  install -Dm644 copying.txt "${pkgdir}/usr/share/licenses/${pkgname}/COPYING"

}
