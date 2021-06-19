PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20210619
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
install="${pkgname}.install"
source=(mirrorlist.mingw32.cn
        mirrorlist.mingw64.cn
        mirrorlist.ucrt64.cn
        mirrorlist.clang64.cn
        mirrorlist.msys.cn)
sha256sums=('4311f6dd02f258b1c96ec2aec262826eda02f3664be921cae546d72c7a994992'
            '6fd3283a2d593a4187e8f9a73ececb29ebd1326ffc363ef1bd6e9d69b51473d2'
            'a9b9d8e782cf5d74bdb7a69fa578256bb41dd3495b5d4a7996bdea6f5ebd00f9'
            '8938a98feaaf077d04e6e82f7b2792b88620331ce317bd6c1f816cdae970cf29'
            'a17602deee0e3107583f2e6d96b2c19125ef5464272ef56bf5b860db83e380dd')

package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.mingw32.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw64.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.ucrt64.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.clang64.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.msys.cn ${pkgdir}/etc/pacman.d/
}
