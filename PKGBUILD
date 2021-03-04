PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20210304
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
install="${pkgname}.install"
source=(mirrorlist.msys.cn
        mirrorlist.mingw32.cn
        mirrorlist.mingw64.cn)
sha256sums=('a17602deee0e3107583f2e6d96b2c19125ef5464272ef56bf5b860db83e380dd'
            '4311f6dd02f258b1c96ec2aec262826eda02f3664be921cae546d72c7a994992'
            '6fd3283a2d593a4187e8f9a73ececb29ebd1326ffc363ef1bd6e9d69b51473d2')

package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.msys.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw32.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw64.cn ${pkgdir}/etc/pacman.d/
}
