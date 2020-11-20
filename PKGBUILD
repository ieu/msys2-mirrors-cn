PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20201120
pkgrel=2
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
source=(mirrorlist.msys.cn
        mirrorlist.mingw32.cn
        mirrorlist.mingw64.cn)
sha256sums=('2ad4826c16e132bb218ef7a6fc3a073b73f8d0cac842261249d6ede905de2e7c'
            'a27b6b31f6172ab4bdd60f134061e4be7dd988f1e1ccbee05a1ec8bfa0fe562a'
            'fca513ec069316f47aa5a4daa9da7833aa7a37b8fcd0ce476fb6e70d899d4e3f')

package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.msys.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw32.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw64.cn ${pkgdir}/etc/pacman.d/
}