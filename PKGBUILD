# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=xdgmenumaker
pkgver=1.4.r5.gdcc48c6
pkgrel=2
pkgdesc="xdgmenumaker creates generating menus using xdg information for blackbox, compizboxmenu, fluxbox, icewm, jwm, pekwm, twm such as ctwm/vtwm and windowmaker."
url="https://github.com/gapan/$pkgname"
arch=(x86_64)
license=('GPLv3')
depends=('python' 'pygobject-devel' 'gobject-introspection' 'python-gobject' 'python-xdg')
optdepends=('txt2tags: to build the manpages')
_commit="dcc48c66110f456dd12780bc13d21260445a323e"
source=("git+https://github.com/gapan/${pkgname}#commit=$_commit")
sha512sums=(SKIP)
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

pkgver() {
	cd "$pkgname"
	git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}	
build() {
  cd "$srcdir/$pkgname"
  make
}

package() {
  cd "$srcdir/$pkgname"
  
  make DESTDIR="$pkgdir" PREFIX=/usr install
}

