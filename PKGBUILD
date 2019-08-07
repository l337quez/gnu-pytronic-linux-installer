# Maintainer: "L337" Ronal Forero Leon (https://ronaldl337.wordpress.com/)
# Maintainer: Ronal Forero <l337.ronald AT gmail DOT com>
pkgname=gnu-pytronic
pkgver=0.1
pkgrel=1
pkgdesc="gnu pytronic is a program developed in python 3. Basically it is a basic tool for the calculation of analog components such as resistors, capacitors and inductors, also transformers"
arch=('i686' 'x86_64')
url="https://github.com/l337quez/GNU-Pytronic"
license=('GPL3')
source=("git+https://github.com/l337quez/gnu-pytronic-linux-installer.git")
md5sums=('6783e657af0ff7c0c3a6c482c50db2a2')
makedepends=('git')
depends=('python3')





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
# Nos dirigimos a la carpeta dist donde esta la aplicacion

  cd /gnu-pytronic-linux-installer/dist
  

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
