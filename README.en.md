MSYS2 mirrors in China

[简体中文](./README.md)

## Usage

### Quick install

```shell
( PKGVER=20210614 PKGREL=1 PKGFILN=pacman-mirrors-cn-${PKGVER}-${PKGREL}-any.pkg.tar.xz ; curl -L -o ${TMP}/${PKGFILN} https://github.com/ieu/msys2-mirrors-cn/releases/download/${PKGVER}-${PKGREL}/${PKGFILN} && pacman -U --needed --noconfirm ${TMP}/${PKGFILN} ; ( [ -f ${TMP}/${PKGFILN} ] && rm ${TMP}/${PKGFILN} ) )
```

### Use prebuilt package

1. Download package from [release page](https://github.com/ieu/msys2-mirrors-cn/releases)

2. Install using `pacman`

```shell
# pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar.xz
```

3. Start using it

```shell
# pacman -Syu
```

### Configure manually

1. Download and save `mirrorlist`(s) you need to `/etc/pacman.d/`

2. Edit `/etc/pacman.conf` and add `mirrorlist`(s) on top of `mirrorlist` list of corresponding repo as below:

```ini
[mingw32]
Include = /etc/pacman.d/mirrorlist.mingw32.cn
Include = /etc/pacman.d/mirrorlist.mingw32

[mingw64]
Include = /etc/pacman.d/mirrorlist.mingw64.cn
Include = /etc/pacman.d/mirrorlist.mingw64

[ucrt64]
Include = /etc/pacman.d/mirrorlist.ucrt64.cn
Include = /etc/pacman.d/mirrorlist.ucrt64

[clang64]
Include = /etc/pacman.d/mirrorlist.clang64.cn
Include = /etc/pacman.d/mirrorlist.clang64

[msys]
Include = /etc/pacman.d/mirrorlist.msys.cn
Include = /etc/pacman.d/mirrorlist.msys
```

You can add all `mirrorlist`s to `pacman.conf` with one line command using `sed`

```shell
# sed -i 's/^\[\(mingw32\|mingw64\|ucrt64\|clang64\|msys\)\]$/\0\nInclude = \/etc\/pacman.d\/mirrorlist.\1.cn/' /etc/pacman.conf
```

3. Start using it

```shell
# pacman -Syu
```

## Build package from source code

1. Install toolchain

```shell
# pacman -S binutils
```

2. Clone this repo

```shell
$ git clone https://github.com/ieu/msys2-mirrors-cn.git
```

3. Build package

```shell
$ makepkg
```

## Mirrors provided

* [TU Open Source Software Mirrors](https://mirrors.tuna.tsinghua.edu.cn/)
* [USTC Open Source Software Mirrors](https://mirrors.ustc.edu.cn/)
* [BFSU Open Source Software Mirrors](https://mirrors.bfsu.edu.cn/)
* [SJTU Linux User Group Software Source Mirrors](https://mirrors.sjtug.sjtu.edu.cn/)
* [NJU Open Source Mirrors](https://mirrors.nju.edu.cn/)
* [Huawei Open Source Mirrors](https://mirrors.huaweicloud.com/)
* [Tencent Software Source](https://mirrors.cloud.tencent.com/)
