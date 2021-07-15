PKGEXT='.pkg.tar.xz'
pkgname=pacman-mirrors-cn
pkgver=20210715
pkgrel=1
pkgdesc='MSYS2 mirror list for use by pacman in China'
arch=('any')
url='https://github.com/ieu/msys2-mirrors-cn'
license=('GPL')
install="${pkgname}.install"
source=(mirrorlist.mingw.cn
        mirrorlist.msys.cn)
sha256sums=('cf9c7aeb423665b7f4adcaf7d7d4d7b79835cb6e157c2ce3656b79b6e0068fd0'
            'a17602deee0e3107583f2e6d96b2c19125ef5464272ef56bf5b860db83e380dd')
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
