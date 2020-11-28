MSYS2 mirrors in China

[简体中文](./README.md)

## Usage

### Use pacman

1. Download package from [release page](https://github.com/ieu/msys2-mirrors-cn/releases)

2. Install using `pacman`

```shell
# pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar
```

3. Start using it

```shell
# pacman -Syu
```

### Manually

1. Download file `mirrorlist.mingw32.cn`, `mirrorlist.mingw32.cn` and `mirrorlist.msys.cn` then save to `/etc/pacman.d`

2. Put mirror list at head of every repo like this:

```ini
[mingw32]
Include = /etc/pacman.d/mirrorlist.mingw32.cn
Include = /etc/pacman.d/mirrorlist.mingw32

[mingw64]
Include = /etc/pacman.d/mirrorlist.mingw64.cn
Include = /etc/pacman.d/mirrorlist.mingw64

[msys]
Include = /etc/pacman.d/mirrorlist.msys.cn
Include = /etc/pacman.d/mirrorlist.msys
```

Or do it with one line command (using `sed`)：
```shell
sed -i 's/^\[\(mingw32\|mingw64\|msys\)\]$/\0\nInclude = \/etc\/pacman.d\/mirrorlist.\1.cn/' /etc/pacman.conf
```

3. Start using it

```shell
# pacman -Syu
```

## Package from source code

1. Install toolchain

```shell
# pacman -S binutils
```

2. Clone this repo

```shell
$ git clone https://github.com/ieu/msys2-mirrors-cn.git
```

3. package

```shell
$ cd msys2-mirrors-cn
$ makepkg -c
```

## Collected mirrors

* [TU Open Source Software Mirrors](https://mirrors.tuna.tsinghua.edu.cn/)
* [USTC Open Source Software Mirrors](https://mirrors.ustc.edu.cn/)
* [BIT Open Source Software Mirrors](https://mirror.bit.edu.cn/)
* [BFSU Open Source Software Mirrors](https://mirrors.bfsu.edu.cn/)
* [SJTU Linux User Group Software Source Mirrors](https://mirrors.sjtug.sjtu.edu.cn/)
* [NJU Open Source Mirrors](https://mirrors.nju.edu.cn/)
* [Huawei Open Source Mirrors](https://mirrors.huaweicloud.com/)
* [Tencent Software Source](https://mirrors.cloud.tencent.com/)
