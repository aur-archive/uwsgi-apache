# Contributor: Kevin Zuber <uKev@knet.eu>, Jonathan Liu <net147@gmail.com>
# Maintainer: Kevin Zuber <uKev@knet.eu>
pkgname=('uwsgi-apache')
_pkgbase=uwsgi
pkgver=1.4.9
pkgrel=1
epoch=
pkgdesc="uWSGI is a fast, self-healing and developer/sysadmin-friendly application container server coded in pure C. Splitted package to support python, python2, ruby (rack), ... "
arch=(i686 x86_64 arm armv6h)
url="http://projects.unbit.it/uwsgi/"
license=('GPL2')
groups=()
depends=(libyaml jansson uwsgi-core apache)
makedepends=(python)
checkdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(http://projects.unbit.it/downloads/$_pkgbase-$pkgver.tar.gz)
noextract=()
md5sums=('3fe995a39e0489621ddcc7acfbd49171')


build() {
  cd "$srcdir/$_pkgbase-$pkgver/apache2"
  apxs -c mod_uwsgi.c
}

package() {
  cd "$srcdir/$_pkgbase-$pkgver/apache2"
  install -D -m755 .libs/mod_uwsgi.so "$pkgdir/usr/lib/httpd/modules/mod_uwsgi.so"
}
