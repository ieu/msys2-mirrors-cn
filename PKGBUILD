PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20201119
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
source=(mirrorlist.msys.cn
        mirrorlist.mingw32.cn
        mirrorlist.mingw64.cn)
sha256sums=('863eb60935f0134774f2e655730f73d2bc05007d0c4488a62f852e43b5e8f48c'
            '847340e19c82dd587c976be217561cc9bd86cf486acbfa5b8c6bcd60a0845fe5'
            'ad8327d1175710206f48900750d0e5d9b73dd5cd6bc66071ed9abb685b4506cc')

package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.msys.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw32.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.mingw64.cn ${pkgdir}/etc/pacman.d/
}