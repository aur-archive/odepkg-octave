_pack=odepkg
pkgname=$_pack-octave
pkgver=0.8.4
pkgrel=2
pkgdesc="A package for Octave for solving ordinary differential equations and more."
arch=('i686' 'x86_64')
url="http://octave.sourceforge.net/$_pack/index.html"
license=('GPLv2+')
depends=('octave>=3.2.0')
makedepends=()
optdepends=()
backup=()
options=()
install=$pkgname.install
source=("http://downloads.sourceforge.net/octave/$_pack-$pkgver.tar.gz")
noextract=("$_pack-$pkgver.tar.gz")
md5sums=('aa79d0352d80c15fa0a978a883d492e6')

build() {
cd "$srcdir"
mkdir -p builddir
octave -q -f --eval "pkg build -verbose -nodeps builddir $_pack-$pkgver.tar.gz"
}

package() {
mkdir -p "$pkgdir/usr/share/octave/packages"
mkdir -p "$pkgdir/usr/lib/octave/packages"
cp "$srcdir/builddir/$_pack-$pkgver.tar.gz" "$pkgdir/usr/share/octave/$_pack.tar.gz"
}
