PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20210717
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
install="${pkgname}.install"
source=(mirrorlist.mingw.cn
        mirrorlist.msys.cn)
sha256sums=('9ffe069aef9003e7c604d22b4f8496e7786a5ca4ff37d43c4092749ec5fc2ecd'
            'ad9973a3c80d235b6fb01988e6323a8cb786baa7f3d0adb1cc4ac611250c1a4e')
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
