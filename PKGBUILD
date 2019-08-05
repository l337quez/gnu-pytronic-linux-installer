# Maintainer: "L337" Ronal Forero Leon (https://ronaldl337.wordpress.com/)
# Maintainer: Ronal Forero <l337.ronald AT gmail DOT com>
pkgname=gnu-pytronic
pkgver=0.1
pkgrel=1
pkgdesc="gnu pytronic is a program developed in python 3. Basically it is a basic tool for the calculation of analog components such as resistors, capacitors and inductors, also transformers"
arch=('i686' 'x86_64')
url="https://github.com/l337quez/GNU-Pytronic"
license=('GPL3')
source=("https://github.com/l337quez/GNU-Pytronic/tree/master/%20GNU%20Linux%20installer/${pkgname}-${pkgver}.tar.gz")
md5sums=('e69996fd39f1285f4a5974c2e9c5a6fa')
makedepends=('git')
depends=('python3')


#        "${pkgname}.patch")
#sha256sums=('03b72397311f555f598028bf5ef800f7449cc76544d9f9833798fc8dafeb1df9'
#            'c952eb32dd59beff9fc5374853b04acde4a60ed8c39934fcd0b66829455d594d')

package() {
#    bsdtar -O -xf "slack-desktop-${pkgver}"*.deb data.tar.xz | bsdtar -C "${pkgdir}" -xJf -

    # Fix hardcoded icon path in .desktop file
#    patch -d "${pkgdir}" -p1 <"${pkgname}".patch

    # Permission fix
#    find "${pkgdir}" -type d -exec chmod 755 {} +

    # Remove all unnecessary stuff
#    rm -rf "${pkgdir}/etc"
#    rm -rf "${pkgdir}/usr/share/lintian"
#    rm -rf "${pkgdir}/usr/share/doc"

#nos vamos al directorio de descarga del source
  cd "${srcdir}/"
  #Descomprimimos el archivo
  tar xvzf ${pkgname}-${pkgver}.tar.gz -C .
  cp -r usr ${pkgdir}

  cd "$pkgdir"
  install -dm 755 "$pkgdir/usr/bin/"
  install -dm 755 "$pkgdir/usr/share/applications/"
  install -dm 755 "$pkgdir/usr/share/pixmaps/"
 
  install -m755 "$srcdir/gnu-pytronic/main" "$pkgdir/usr/bin/"
  install -m644 "$srcdir/gnu-pytronic/Sources/pytronics.png" "$pkgdir/usr/share/pixmaps/"



#Creamos el acceso directo
cat > $pkgdir/usr/share/applications/$pkgname.desktop << EOF
[Desktop Entry]
Version=0.002
Name=GNU Pytronic
Comment=pytronic is a program developed in python 3. Basically it is a basic tool for the calculation of analog components such as resistors, capacitors and inductors, also transformers.
Exec=python main.py
Icon=/usr/share/pixmaps/pytronics.png
Terminal=false
Type=Application
StartupNotify=true
Categories=Electronics;
EOF

}
