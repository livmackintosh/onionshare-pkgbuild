# Maintainer: Simon Hanna <simon dot hanna at serve-me dot info>
pkgname=onionshare
pkgver=1.2.dev1
pkgrel=1
pkgdesc="Lets you securely and anonymously share a file of any size with someone"
url="https://github.com/micahflee/onionshare"
arch=('any')
license=('GPL3')
makedepends=('python-setuptools')
checkdepends=('python-pytest' 'python-nose')
depends=('stem' 'python-flask' 'python-pysocks')
optdepends=(
          'python-pyqt5: to run onionshare-gui'
          'tor-browser-en: before you can share a file, you need to open Tor Browser'
          'tor-messenger-bin: tor-messenger can be used as an alternative to Tor Browser'
          )
source=(https://github.com/livmackintosh/onionshare/archive/v$pkgver.tar.gz)
sha512sums=('66fcc029f5c62410dd8fe786f3acaf78e0ec0442c831ee6daa19ae483a825b6ccefcb83813b6114bba4e0e19393973b35c7025a4acda7ec7262b927178092b8f')

build() {
 	cd "$srcdir/onionshare-$pkgver"
  python setup.py build
}

check() {
 	cd "$srcdir/onionshare-$pkgver"
  nosetests test
}

package() {
	cd "$srcdir/onionshare-$pkgver"
	python setup.py install --root="$pkgdir/" --optimize=1
	install -D -m 644 install/onionshare.desktop "${pkgdir}/usr/share/applications/onionshare.desktop"
	install -D -m 644 install/onionshare80.xpm "${pkgdir}/usr/share/pixmaps/onionshare80.xpm"
}

# vim:set ts=2 sw=2 et:
