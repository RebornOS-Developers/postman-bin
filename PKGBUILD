# Maintainer: Jay Ta'ala <jay@jaytaala.com>
# Contributor: Claudio d'Angelis <claudiodangelis at gmail dot com>
# PKGBUILD review by Rafael from RebornOS

pkgname=postman-bin
pkgver=9.0.5
pkgrel=1
pkgdesc="Build, test, and document your APIs faster"
provides=('postman')
conflicts=('postman')
arch=('x86_64')
url="https://www.getpostman.com"
options=(!strip)
license=('custom')
source=(
	"Postman-linux-x64-${pkgver}.tar.gz::https://dl.pstmn.io/download/version/${pkgver}/linux64"
	"postman.desktop"
)
depends=(libxss nss gtk3)
sha256sums=('fbdc4f134a9caebd52215d11310e31a4f4003844d398a89a4fa9519977d948fc'
            '74b2d8570658e207e31f729e7f4768952252383aee7c695218d077bd0ef13245')
package() 
{
  mkdir -p ${pkgdir}/opt/postman
  mkdir -p ${pkgdir}/usr/bin
  mkdir -p ${pkgdir}/usr/share/applications
  mkdir -p ${pkgdir}/usr/share/icons/hicolor/128x128/apps
  cp -r ${srcdir}/Postman/* ${pkgdir}/opt/postman
  ln -s /opt/postman/Postman ${pkgdir}/usr/bin/postman
  # Desktop file
  install -D -m644 postman.desktop ${pkgdir}/usr/share/applications/
  # Icon
  install -d -m755 ${pkgdir}/usr/share/icons/hicolor/128x128/apps
  ln -s /opt/postman/app/resources/app/assets/icon.png \
  ${pkgdir}/usr/share/icons/hicolor/128x128/apps/postman.png
}
