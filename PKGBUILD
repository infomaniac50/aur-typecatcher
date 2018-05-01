# Maintainer: Marcos Heredia <chelqo@gmail.com>

pkgname=typecatcher
pkgver=0.3.r0.g0a4feaf
pkgrel=1
pkgdesc="Download Google webfonts for off-line use"
arch=('i686' 'x86_64')
url="https://launchpad.net/typecatcher"
screenshot="http://andrewsomething.files.wordpress.com/2012/11/selection_005.png"
license=('GPL3')
makedepends=('git')
depends=('python3' 'python-distutils-extra' 'python-gobject' 'yelp' 'webkit2gtk' 'gobject-introspection' 'gtk3')
source=('typecatcher::git+http://github.com/andrewsomething/typecatcher#tag=0.3')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${pkgname}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "$srcdir/${pkgname}"
  python3 setup.py build
}

package() {
  cd "$srcdir/${pkgname}"
  python3 setup.py install --root=$pkgdir --optimize=1
  install -dm755 ${pkgdir}/usr/share/licenses/${pkgname}/
  install -Dpm644 COPYING ${pkgdir}/usr/share/licenses/${pkgname}/
  install -dm755 ${pkgdir}/usr/share/doc/${pkgname}/
  install -Dpm644 AUTHORS ${pkgdir}/usr/share/doc/${pkgname}/
}
