# Maintainer: Roman Kyrylych <Roman.Kyrylych@gmail.com>
# Contributor: Roman Kyrylych <Roman.Kyrylych@gmail.com>

pkgname=mc-colorer
pkgver=20060530_0.9
pkgrel=4
_realname="mccolorer-20060530-0.9"
pkgdesc="Midnight Commander mod with Colorer-take5 syntax engine"
arch=('i686' 'x86_64')
url="http://colorer.sourceforge.net/mc.html"
license=("GPL")
depends=('e2fsprogs' 'glib2' 'gpm' 'colorer')
optdepends=('p7zip: support for 7zip archives')
conflicts=('mc')
provides=('mc')
source=(http://downloads.sourceforge.net/sourceforge/colorer/$_realname.tar.bz2)
md5sums=('83ffea150d6853cbc8a9422d5c21542c')

build() {
  cd "$srcdir/$_realname"
  ./configure --prefix=/usr --with-x --libexecdir=/usr/lib/mc-colorer \
 	--mandir=/usr/share || return 0

  make || return 1
  make DESTDIR="$pkgdir" install

  #FS#18573
  rm -f "$pkgdir/usr/share/mc/extfs/u7z" || return 1
}

