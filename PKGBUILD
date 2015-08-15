# Maintainer : ziggi <xziggix@gmail.com>
pkgname='gnustep-opal-git'
pkgver=20130129
pkgrel=1
pkgdesc='Opal is a vector drawing library with an API similar to Quartz 2D.'
arch=('i686' 'x86_64')
url='http://www.cocoadev.com/index.pl?CoreGraphics'
license=('LGPL')
makedepends=('gnustep-base' 'gnustep-corebase-git' 'cairo' 'libjpeg-turbo' 'libpng' 'libtiff' 'lcms')
provides=('gnustep-opal')

_gitroot='git://github.com/gnustep/gnustep-opal.git'
_gitname='gnustep-opal'

build () {
	cd "${srcdir}"
	if [ -d "${_gitname}" ] ; then
		msg "The files are updated"
	else
		git clone "${_gitroot}"
	fi
	cd "${_gitname}"
	make
}

package() {
	cd "${_gitname}"
	make DESTDIR="$pkgdir" install
}
