# Contributor: Adam Hani Schakaki <adam@schakaki.net>
# Maintainer: Ner0

pkgname=muffin-wm
pkgver=1.1.2
pkgrel=1
pkgdesc="Cinnamon window manager based on Mutter"
arch=('i686' 'x86_64')
url="https://github.com/linuxmint/muffin"
license=('GPL')
depends=('clutter' 'gconf' 'gobject-introspection' 'gsettings-desktop-schemas' 'libcanberra' 'libxxf86vm' 'startup-notification' 'zenity' 'dconf')
makedepends=('libltdl' 'intltool' 'gnome-doc-utils' 'pkg-config')
conflicts=('muffin-git')
options=('!libtool' '!emptydirs')
install=$pkgname.install
source=("$pkgname-$pkgver.tar.gz::https://github.com/linuxmint/muffin/tarball/$pkgver")
md5sums=('0950fa5c00a165c7fed73b0898d072d5')

build() {
  cd linuxmint-muffin-*

  sed -i 's/\ --warn-all\ --warn-error//' src/Makefile.{am,in}

  autoreconf -vfi
  PYTHON=python2 ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib/muffin --localstatedir=/var --disable-static --disable-schemas-compile
  make ${MAKEFLAGS}
}

package() {
  cd linuxmint-muffin-*
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
