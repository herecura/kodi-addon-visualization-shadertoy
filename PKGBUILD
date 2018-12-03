# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-visualization-shadertoy
epoch=1
pkgver=1.1.8
_codename=Leia
pkgrel=3
pkgdesc="Shadertoy visualizer for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/visualization.shadertoy'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-visualization')
depends=('kodi' 'p8-platform')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/visualization.shadertoy/archive/$pkgver-$_codename.tar.gz")
sha512sums=('5cee18db177c0cc61bc46a4d457b559bd1a023d3ff51261eee8d4c4828df77571beda12dd726f30554bd16c7ad67e12d836c5a211a3d55321d92551eb337ddc6')

build() {
    cd "visualization.shadertoy-$pkgver-$_codename"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
    cd "visualization.shadertoy-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

