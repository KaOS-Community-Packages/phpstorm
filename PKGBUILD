pkgname=phpstorm
pkgver=2023.3.4
_build=233.14475.35
_pkgdir=PhpStorm-${_build}
pkgrel=1
pkgdesc="Lightning-smart PHP IDE"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/phpstorm/"
license=('custom: https://www.jetbrains.com/company/useterms.html')
install='phpstorm.install'
source=("https://download.jetbrains.com/webide/PhpStorm-${pkgver}.tar.gz"
        "${pkgname}.desktop")
md5sums=('a68b5ad8079c0de0960b059f8d35157b'
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
