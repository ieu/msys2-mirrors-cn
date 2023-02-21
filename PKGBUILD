pkgname=pacman-mirrors-cn
pkgver=20230221
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
install="${pkgname}.install"
source=(mirrorlist.mingw.cn
        mirrorlist.msys.cn)
sha256sums=('f0adb6f97e7899a460460726a9d9e9af341eaf14d23922d41cee442f3edc7cc0'
            '5b16b1349fadaf681cc1636faeeb44718f15194184fa3bced0a85bd96f5ad640')
backup=(
  'etc/pacman.d/mirrorlist.msys.cn'
  'etc/pacman.d/mirrorlist.mingw.cn'
  'etc/pacman.d/mirrorlist.mingw32.cn'
  'etc/pacman.d/mirrorlist.mingw64.cn'
  'etc/pacman.d/mirrorlist.ucrt64.cn'
  'etc/pacman.d/mirrorlist.clang64.cn'
  'etc/pacman.d/mirrorlist.clang32.cn'
)
package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.msys.cn ${pkgdir}/etc/pacman.d/

  # For backwards compatibility
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/mirrorlist.mingw32.cn
  sed -s 's|$repo|i686|g' -i ${pkgdir}/etc/pacman.d/mirrorlist.mingw32.cn
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/mirrorlist.mingw64.cn
  sed -s 's|$repo|x86_64|g' -i ${pkgdir}/etc/pacman.d/mirrorlist.mingw64.cn
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/mirrorlist.ucrt64.cn
  sed -s 's|$repo|ucrt64|g' -i ${pkgdir}/etc/pacman.d/mirrorlist.ucrt64.cn
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/mirrorlist.clang64.cn
  sed -s 's|$repo|clang64|g' -i ${pkgdir}/etc/pacman.d/mirrorlist.clang64.cn
  install -m644 ${srcdir}/mirrorlist.mingw.cn ${pkgdir}/etc/pacman.d/mirrorlist.clang32.cn
  sed -s 's|$repo|clang32|g' -i ${pkgdir}/etc/pacman.d/mirrorlist.clang32.cn
}
