# $Id: PKGBUILD 82 2009-07-17 19:56:55Z aaron $
# Contributor: Mateusz Herych <heniekk@gmail.com>
# Contributor: failure <failure@linuxers.cl>

pkgname=kooldock
pkgver=0.4.7
pkgrel=2
pkgdesc="A KDE Docker with great effects"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/kooldock"
license=('GPL')
depends=('kdelibs3')
source=(http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.bz2
	gcc43.patch)
md5sums=('00103ac218865125de91bdbc4507f7d8'
         '94be9886053d9379f749a8334c5787ec')

build() {
	source /etc/profile.d/qt3.sh
	source /etc/profile.d/kde3.sh
	cd $srcdir/$pkgname
	patch -p0 < ../gcc43.patch
	./configure --prefix=/opt/kde \
		--without-arts
	make || return 1
	make DESTDIR=$pkgdir install || return 1
}
