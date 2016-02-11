# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Giampaolo Mancini <giampaolo@trampolineup.com>
pkgname=pam-python
pkgver=1.0.4
pkgrel=1
epoch=
pkgdesc="Enables PAM modules to be written in Python"
arch=("any")
url="http://pam-python.sourceforge.net"
license=('AGPL3')
groups=()
depends=("python2" "pam")
makedepends=("python-sphinx" "sudo")
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("https://sourceforge.net/projects/$pkgname/files/$pkgname-$pkgver-1/$pkgname-$pkgver.tar.gz/download"
	"$pkgname-${pkgver}_python2.patch")
noextract=()
md5sums=('55176ff034ab4417768232d98e9b84d5'
         '34e23d62572bb6b4c3c6a8e409546621')
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver"
	patch -p1 -i "$srcdir/$pkgname-${pkgver}_python2.patch"
}

build() {
	cd "$pkgname-$pkgver"
	make 
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" LIBDIR=/usr/lib/security install
}
