# Contributor : Moostik
# Maintainer: MrMen <tetchet at gmail dot com>

pkgname=drgeo2
pkgver=15.04
pkgrel=1
pkgdesc="Interactive geometry tool for primary and secondary level"
arch=('any')
url='http://www.drgeo.eu/'
license=('LGPL3') 
depends=('squeak-vm')
source=("https://launchpad.net/drgeo/trunk/${pkgver}/+download/DrGeo.app-${pkgver}a.zip"
	"${pkgname}.png"
	"${pkgname}.desktop"
	"${pkgname}.sh")
md5sums=('1593770090b4fe3a24356fef2f499648'
         'cacac23b5173fa18411719ce352a982e'
         '494e9e8a5e28e3c5884525c4927435f5'
         'eab4b38964345173b1714d2acc845598')


package () {
  # Installing application
  cd "${srcdir}/DrGeo.app/Contents/Resources"

  for _lang in "de" "es" "fr" 
  do 
    install -D -m644 "locale/${_lang}/LC_MESSAGES/DrGeoII.mo" \
      "${pkgdir}/usr/share/${pkgname}/locale/${_lang}/LC_MESSAGES/DrGeoII.mo"
  done

  cd "${srcdir}/DrGeo.app/Contents/"
  mkdir "${pkgdir}/usr/share/${pkgname}/Contents"
  cp -r "Resources" "${pkgdir}/usr/share/${pkgname}/Contents/"
  cp -r "Linux" "${pkgdir}/usr/share/${pkgname}/Contents/"
  chmod -R 755 "${pkgdir}/usr/share/${pkgname}/Contents/"
  chmod -R 755 "${pkgdir}/usr/share/${pkgname}/Contents/"

  
  install -D -m644 "${srcdir}/DrGeo.app/DrGeo.sh" "${pkgdir}/usr/share/${pkgname}/"
  install -D -m644 "${srcdir}/DrGeo.app/splash.bmp" "${pkgdir}/usr/share/${pkgname}/"
  # Installing menu item
  cd "${srcdir}"
  install -D -m755 "${pkgname}.sh" "${pkgdir}/usr/bin/${pkgname}"
  install -D -m755 "${pkgname}.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
  install -D -m755 "${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
