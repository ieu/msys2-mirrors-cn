MSYS2 中国镜像站

[English](./README.en.md)

## 使用方法

### 快速安装

```shell
( PKGVER=20210619 PKGREL=1 PKGFILN=pacman-mirrors-cn-${PKGVER}-${PKGREL}-any.pkg.tar.xz ; curl -L -o ${TMP}/${PKGFILN} https://github.com/ieu/msys2-mirrors-cn/releases/download/${PKGVER}-${PKGREL}/${PKGFILN} && pacman -U --needed --noconfirm ${TMP}/${PKGFILN} ; ( [ -f ${TMP}/${PKGFILN} ] && rm ${TMP}/${PKGFILN} ) )
```

### 使用预构建镜像包

1. 从 [release page](https://github.com/ieu/msys2-mirrors-cn/releases) 下载镜像包

2. 使用 `pacman` 安装镜像包

```shell
# pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar.xz
```

3. 开始使用

```shell
# pacman -Syu
```

### 手动设置

1. 下载所需镜像列表文件并保存至 `/etc/pacman.d/`

2. 编辑 `/etc/pacman.conf`，在对应仓库镜像列表前添加上述镜像列表文件

示例：
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

使用 `sed` 可快速添加镜像列表文件

```shell
# sed -i 's/^\[\(mingw32\|mingw64\|ucrt64\|clang64\|msys\)\]$/\0\nInclude = \/etc\/pacman.d\/mirrorlist.\1.cn/' /etc/pacman.conf
```

4. 开始使用

```shell
# pacman -Syu
```

## 从源码构建镜像包

1. 安装 toolchain

```shell
# pacman -S binutils
```

2. 克隆代码

```shell
$ git clone https://github.com/ieu/msys2-mirrors-cn.git
```

3. 打包

```shell
$ makepkg
```

## 收录站点

* [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)
* [中国科学技术大学开源软件镜像](https://mirrors.ustc.edu.cn/)
* [北京外国语大学开源软件镜像站](https://mirrors.bfsu.edu.cn/)
* [上海交通大学 Linux 用户组 软件源镜像服务](https://mirrors.sjtug.sjtu.edu.cn/)
* [南京大学开源镜像站](https://mirrors.nju.edu.cn/)
* [华为开源镜像站](https://mirrors.huaweicloud.com/)
* [腾讯软件源](https://mirrors.cloud.tencent.com/)
