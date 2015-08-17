# Maintainer: Tommi Helineva <tommi.helineva+aur@gmail.com>
pkgname=tilitin
pkgver=1.5.0
pkgrel=1
pkgdesc="A Finnish accounting software"
arch=('any')
url="http://helineva.net/tilitin/"
license=('GPL3')
depends=('java-environment')
makedepends=('apache-ant')
install='tilitin.install'
source=(tilitin.sh tilitin.desktop http://helineva.net/tilitin/tilitin-${pkgver}-src.zip)
sha1sums=('7c244c5aee25582597491895d4ecb876ed809b7e'
          'd7ad246707019abb960458a9a01501a2a4fd65a2'
          'b739aad944263888ab90312400cb4dc85275c7eb')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  /usr/bin/ant
}

package() {
  install -D -m 755 $startdir/tilitin.sh $pkgdir/usr/bin/tilitin
  install -D -m 644 $startdir/tilitin.desktop $pkgdir/usr/share/applications/tilitin.desktop
  cd "$srcdir/$pkgname-$pkgver"
  install -D -m 644 dist/tilitin.jar $pkgdir/usr/lib/tilitin/tilitin.jar
  mkdir -p $pkgdir/usr/lib/tilitin/tilikarttamallit
  install -D -m 644 lib/itext.jar $pkgdir/usr/lib/tilitin/itext.jar
  install -D -m 644 lib/postgresql-jdbc.jar $pkgdir/usr/lib/tilitin/postgresql-jdbc.jar
  install -D -m 644 lib/sqlite-jdbc.jar $pkgdir/usr/lib/tilitin/sqlite-jdbc.jar
  install -m 644 tilikarttamallit/*.jar $pkgdir/usr/lib/tilitin/tilikarttamallit/
  install -D -m 644 src/kirjanpito/ui/resources/tilitin-24x24.png $pkgdir/usr/share/icons/hicolor/24x24/apps/tilitin.png
  install -D -m 644 src/kirjanpito/ui/resources/tilitin-32x32.png $pkgdir/usr/share/icons/hicolor/32x32/apps/tilitin.png
  install -D -m 644 src/kirjanpito/ui/resources/tilitin-48x48.png $pkgdir/usr/share/icons/hicolor/48x48/apps/tilitin.png
}
