pkgname=phpstorm
pkgver=2017.1.3
_build=171.4424.11
pkgrel=1
pkgdesc="Lightweight and Smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="http://www.jetbrains.com/phpstorm/"
license=('custom')
install='phpstorm.install'
source=(https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz
        phpstorm.desktop)
sha256sums=('1bc8b34a668101fc9b6299ebb2a990a242317d194c1095088474c343b4183bcd'
            '58de11c860bfe1233db010b57d632aad513419fc73839a035219021f06a413ec')

package() {
  install -d -m 755 ${pkgdir}/opt/
  cp -a ${srcdir}/PhpStorm-${_build} $pkgdir/opt/${pkgname}
  sed -i 's/lcd/on/' $pkgdir/opt/${pkgname}/bin/phpstorm64.vmoptions
  echo "-Dswing.aatext=true" >> $pkgdir/opt/${pkgname}/bin/phpstorm64.vmoptions
  install -d -m 755 ${pkgdir}/usr/bin/
  ln -s /opt/$pkgname/bin/${pkgname}.sh $pkgdir/usr/bin/${pkgname}
  install -d -m 755 ${pkgdir}/usr/share/applications/
  install -D -m 644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/
  install -d -m 755 ${pkgdir}/usr/share/pixmaps/
  install -D -m 644 "${pkgdir}/opt/${pkgname}/bin/phpstorm.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
}
