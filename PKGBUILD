pkgname=phpstorm
pkgver=2024.1
_build=241.14494.237
_pkgdir=PhpStorm-${_build}
pkgrel=2
pkgdesc="Lightning-smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/phpstorm/"
license=('custom: https://www.jetbrains.com/company/useterms.html')
install='phpstorm.install'
source=("https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz"
        "${pkgname}.desktop")
md5sums=('afdd5051c262d1a42b0a8c659b662f4e'
         'edb8c8f0a9899081c16a789014922c1a')

package() {
    install -dm 755 ${pkgdir}/opt/
    install -dm 755 ${pkgdir}/usr/bin/
    install -dm 755 ${pkgdir}/usr/share/applications/
    install -dm 755 ${pkgdir}/usr/share/icons/hicolor/scalable/apps/
    
#     rm -rf ${_pkgdir}/jbr # DO NOT COMMIT IF UNCOMMENTED, only if  you have installed jdk/openjdk version >= 17 in your system
    rsync -rtl "${_pkgdir}"/ ${pkgdir}/opt/${pkgname}

    ln -s /opt/${pkgname}/bin/${pkgname}.sh ${pkgdir}/usr/bin/${pkgname}
    install -Dm 644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/
    install -Dm 644 ${pkgdir}/opt/${pkgname}/bin/${pkgname}.svg ${pkgdir}/usr/share/icons/hicolor/scalable/apps/${pkgname}.svg
}
