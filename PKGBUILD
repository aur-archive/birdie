# Maintainer: Ivo Nunes <ivoavnunes at gmail dot com>

pkgname="birdie"
pkgver=1.1
pkgrel=2
pkgdesc="Twitter client for Linux"
arch=('i686' 'x86_64')
url="http://birdieapp.github.io"
license=('GPL3')
depends=('glib2' 'gtk3' 'libgee06' 'libwnck3' 'libx11' 'hicolor-icon-theme' 'cairo' 'pango' )
makedepends=('libpurple' 'gtksourceview3' 'desktop-file-utils' 'hicolor-icon-theme' 'intltool' 'vala' 'cmake' 'rest' 'json-glib' 'libnotify' 'libwnck3' 'libcanberra' 'webkitgtk' 'sqlite' 'libxtst')
options=('!libtool')
conflicts=('birdie-git' 'birdie-bzr')
provides=('birdie')
install="${pkgname}.install"
source=(https://github.com/birdieapp/birdie/archive/1.1.zip)
md5sums=('8d56a369ba09ed7bd4deea798cb07a4b')

build() {
    cd ${srcdir}/${pkgname}-${pkgver}
    cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr -DGSETTINGS_COMPILE=OFF
    make ${MAKEFLAGS}
}

package() {
    cd ${srcdir}/${pkgname}-${pkgver}
    make GCONF_DISABLE_MAKEFILE_SCHEMA_INSTALL=1 DESTDIR="${pkgdir}/" install
}
