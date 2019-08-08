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
md5sums=('SKIP')
makedepends=('git')
depends=('python3')




package() {

# Nos vamos al directorio de descarga del source
  cd "${srcdir}/gnu-pytronic-linux-installer"

   #Descomprimimos el archivo
  tar -xvzf ${pkgname}-${pkgver}.tar.gz -C .
 # cp -r usr ${pkgdir}
  echo ${pkgdir}


# Nos dirigimos a la carpeta dist donde esta la aplicacion

  cd "$pkgdir"

# Creamos los directorios correspondientes  
  install -dm 755 "$pkgdir/usr/bin"
  install -dm 755 "$pkgdir/usr/share/"
  install -dm 755 "$pkgdir/usr/share/applications/"
  install -dm 755 "$pkgdir/usr/share/pixmaps/"
  install -dm 755 "$pkgdir/usr/share/gnu-pytronic"

# Programa
  install -Dm755 "$srcdir/gnu-pytronic-linux-installer/dist/gnu-pytronic.desktop" "$pkgdir/usr/bin/gnu-pytronic.desktop"
  
# Copiamos los archivos del binario  
  cp -r "$srcdir/gnu-pytronic-linux-installer/build" "$pkgdir/usr/share/gnu-pytronic/build"
  cp -r "$srcdir/gnu-pytronic-linux-installer/dist" "$pkgdir/usr/share/gnu-pytronic/dist"  
  #cp -r "$srcdir/gnu-pytronic-linux-installer/dist/pytronics.png" "$pkgdir/usr/share/dist"
  
  install -m755 "$srcdir/gnu-pytronic-linux-installer/dist/main" "$pkgdir/usr/share/gnu-pytronic/dist/main"
  install -m644 "$srcdir/gnu-pytronic-linux-installer/dist/pytronics.png" "$pkgdir/usr/share/pixmaps/"







}

