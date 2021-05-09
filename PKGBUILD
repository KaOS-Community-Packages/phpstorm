
pkgname=phpstorm
pkgver=2021.1.2
_build=211.7142.44
pkgrel=1
pkgdesc="Lightweight and Smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/phpstorm/"
license=('custom: https://www.jetbrains.com/company/useterms.html')
install='phpstorm.install'
depends=('openjdk')
source=("https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz"
        "${pkgname}.desktop")
md5sums=('9de6f57ac63b6fcc60750d2f7fe80e09'
         'eee7cb12e0c77e817187a48e405999e7')

package() {
    install -d -m 755 ${pkgdir}/opt/
    install -d -m 755 ${pkgdir}/usr/bin/
    install -d -m 755 ${pkgdir}/usr/share/applications/
    install -d -m 755 ${pkgdir}/usr/share/icons/hicolor/128x128/apps/
    
    cd ${srcdir}
    cp -a PhpStorm-${_build} ${pkgdir}/opt/${pkgname}
    sed -i 's/lcd/on/' ${pkgdir}/opt/${pkgname}/bin/phpstorm64.vmoptions
    echo "-Dswing.aatext=true" >> ${pkgdir}/opt/${pkgname}/bin/phpstorm64.vmoptions

    ln -s /opt/${pkgname}/bin/${pkgname}.sh ${pkgdir}/usr/bin/${pkgname}
    install -D -m 644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/
    install -D -m 644 ${pkgdir}/opt/${pkgname}/bin/${pkgname}.svg ${pkgdir}/usr/share/icons/hicolor/128x128/apps/${pkgname}.svg
}
