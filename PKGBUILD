pkgname=phpstorm
pkgver=2016.1
_build=145.258.2
pkgrel=1
pkgdesc="Lightweight and Smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="http://www.jetbrains.com/${pkgname}/"
license=('custom')
install='phpstorm.install'
source=(https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz
        phpstorm.desktop)
sha256sums=('48b3b1d4e4dec954bb224193aea367b6aa6893d286c0e022775e9f81527251ce'
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
  install -D -m 644 "${pkgdir}/opt/${pkgname}/bin/webide.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
}
