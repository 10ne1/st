# Maintainer: mar77i <mar77i at mar77i dot ch>
# Past Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: Scytrin dai Kinthra <scytrin@gmail.com>

pkgname=st-git
_pkgname=st
pkgver=0.8.1.21.g9411120
pkgrel=1
pkgdesc='Simple virtual terminal emulator for X'
url='http://st.suckless.org/'
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
epoch=1

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	git describe --tags |sed 's/-/./g'
}

build() {
	cd ..
	git clean -fd
	make clean
	mkdir pkg src
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 DESTDIR="src"
}

package() {
	cd ..
	make PREFIX=/usr DESTDIR="${pkgdir}" install
}
