pkgname=phpstorm
pkgver=2023.3.3
_build=233.14015.96
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
md5sums=('90bbb931eee8cd18f780d65421a7d570'
         'edb8c8f0a9899081c16a789014922c1a')

package() {
    install -d -m 755 ${pkgdir}/opt/
    install -d -m 755 ${pkgdir}/usr/bin/
    install -d -m 755 ${pkgdir}/usr/share/applications/
    install -d -m 755 ${pkgdir}/usr/share/icons/hicolor/scalable/apps/
    
    rsync -rtl "${_pkgdir}"/ ${pkgdir}/opt/${pkgname}

    ln -s /opt/${pkgname}/bin/${pkgname}.sh ${pkgdir}/usr/bin/${pkgname}
    install -Dm 644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/
    install -Dm 644 ${pkgdir}/opt/${pkgname}/bin/${pkgname}.svg ${pkgdir}/usr/share/icons/hicolor/scalable/apps/${pkgname}.svg
}
