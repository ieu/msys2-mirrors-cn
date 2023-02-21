MSYS2 mirrors in China

[简体中文](./README.md)

## NOTICE

Official `pacman-mirrors` has included all mirrors this project originally collected.

This project and package it provided should no longer be used.

Use command below if you want to comment out any mirror that is not located in China:

```shell
sed -i '/^Server/{/\.cn/!s/^/#/}' /etc/pacman.d/mirrorlist.*
```

## Usage

### Quick install

```shell
( PKGVER=20230221 PKGREL=1 PKGFILN=pacman-mirrors-cn-${PKGVER}-${PKGREL}-any.pkg.tar.zst ; curl -L -o ${TMP}/${PKGFILN} https://github.com/ieu/msys2-mirrors-cn/releases/download/${PKGVER}-${PKGREL}/${PKGFILN} && pacman -U --needed --noconfirm ${TMP}/${PKGFILN} ; ( [ -f ${TMP}/${PKGFILN} ] && rm ${TMP}/${PKGFILN} ) )
```

### Use prebuilt package

1. Download package from [release page](https://github.com/ieu/msys2-mirrors-cn/releases)

2. Install using `pacman`

```shell
pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar.zst
```

3. Start using it

```shell
pacman -Syu
```

### Configure manually

1. Download and save `mirrorlist`(s) you need to `/etc/pacman.d/`

2. Edit `/etc/pacman.conf` and add `mirrorlist`(s) on top of `mirrorlist` list of corresponding repo as below:

```ini
[clangarm64]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[mingw32]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[mingw64]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[ucrt64]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[clang32]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[clang64]
Include = /etc/pacman.d/mirrorlist.mingw.cn
Include = /etc/pacman.d/mirrorlist.mingw

[msys]
Include = /etc/pacman.d/mirrorlist.msys.cn
Include = /etc/pacman.d/mirrorlist.msys
```

You can add all `mirrorlist`s to `pacman.conf` with one line command using `sed`

```shell
sed -i -e '/^\[\(clangarm64\|mingw32\|mingw64\|ucrt64\|clang32\|clang64\)\]$/a Include = \/etc\/pacman.d\/mirrorlist.mingw.cn' -e '/^\[msys\]$/a Include = \/etc\/pacman.d\/mirrorlist.msys.cn' /etc/pacman.conf
```

3. Start using it

```shell
pacman -Syu
```

## Build package from source code

1. Install toolchain

```shell
pacman -S binutils
```

2. Clone this repo

```shell
git clone https://github.com/ieu/msys2-mirrors-cn.git
```

3. Build package

```shell
makepkg
```

## Mirrors included

* [BFSU Open Source Software Mirrors](https://mirrors.bfsu.edu.cn/)
* [TU Open Source Software Mirrors](https://mirrors.tuna.tsinghua.edu.cn/)
* [USTC Open Source Software Mirrors](https://mirrors.ustc.edu.cn/)
* [NJU Open Source Mirrors](https://mirrors.nju.edu.cn/)
* [HIT Open Source Mirrors](https://mirrors.hit.edu.cn/)
* [SJTU Linux User Group Software Source Mirrors](https://mirrors.sjtug.sjtu.edu.cn/)
* [BIT OSS Mirrors Service](https://mirrors.bit.edu.cn/)
* [Alibaba Open Source Mirrors](https://developer.aliyun.com/mirror/)
* [ISCAS Open Source Mirrors](https://mirror.iscas.ac.cn/)
* [Tencent Software Source](https://mirrors.cloud.tencent.com/)