# Maintainer: Pier Luigi Fiorini <pierluigi.fiorini@gmail.com>

pkgname=libcommuni-git
pkgver=20141123.d7fe805
pkgrel=1
pkgdesc="A cross-platform IRC framework written with Qt"
arch=('i686' 'x86_64')
url="https://github.com/communi/communi"
license=('LGPL2.1')
depends=('qt5-base')
makedepends=('gcc' 'git')
conflicts=('libcommuni')
provides=('libcommuni')
source=('git://github.com/communi/libcommuni.git')
md5sums=('SKIP')

pkgver() {
	cd libcommuni
	echo "$(git log -1 --format="%cd" --date=short | tr -d '-').$(git log -1 --format="%h")"
}

build() {
	cd libcommuni

	./configure \
		-prefix /usr \
		-headerdir /usr/include \
		-featuredir /usr/lib/qt/mkspecs/features
	make
}

package() {
	cd libcommuni
	make INSTALL_ROOT="${pkgdir}" install
}
