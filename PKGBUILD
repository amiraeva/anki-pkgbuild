# Maintainer: amiraeva <amersafdari@gmail.com>
pkgname=anki-fresh
pkgver=2.1.21
pkgrel=1
pkgdesc="Helps you remember facts (like words/phrases in a foreign language) efficiently. Updated to upstream at the cost of package bloat."
url=('https://apps.ankiweb.net/')
license=('AGPL3')
arch=('x86_64')
provides=('anki')
conflicts=('anki' 'anki20')
source=("https://github.com/ankitects/anki/releases/download/$pkgver/anki-$pkgver-linux-amd64.tar.bz2")
md5sums=('5edc313170700cd4f486594ebc49e9fc')

# TODO: figure out how to build from source and use system libs/packages instead of the blob that we're copying over
package() {
    cd "$srcdir/anki-$pkgver-linux-amd64"

    mkdir -p "$pkgdir"/usr/share/anki
    cp -av * "$pkgdir"/usr/share/anki/
    mkdir -p $pkgdir/usr/bin
    ln -sf /usr/share/anki/bin/anki $pkgdir/usr/bin/
    mkdir -p $pkgdir/usr/share/pixmaps
    mkdir -p $pkgdir/usr/share/applications
    mkdir -p $pkgdir/usr/share/man/man1

    cd $pkgdir/usr/share/anki && (\
    mv anki.xpm anki.png $pkgdir/usr/share/pixmaps/;\
    mv anki.desktop $pkgdir/usr/share/applications/;\
    mv anki.1 $pkgdir/usr/share/man/man1/)
}
