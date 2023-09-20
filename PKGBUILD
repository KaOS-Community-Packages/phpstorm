pkgname=phpstorm
pkgver=2023.2.2
_build=232.9921.55
pkgrel=1
pkgdesc="Lightning-smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/phpstorm/"
license=('custom: https://www.jetbrains.com/company/useterms.html')
install='phpstorm.install'
source=("https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz"
        "${pkgname}.desktop")
md5sums=('38423aeeebfb74755ece3f03b610e26d'
         'edb8c8f0a9899081c16a789014922c1a')

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
