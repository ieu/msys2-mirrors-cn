MSYS2 中国镜像站

[English](./README.en.md)

## 说明

官方软件包 `pacman-mirrors` 已收录本项目原先收集的镜像站。

本项目及其软件包不再推荐使用。

如有需求可使用以下命令快速选取所有位于中国的镜像地址：

```shell
sed -i '/^Server/{/\.cn/!s/^/#/}' /etc/pacman.d/mirrorlist.*
```

## 使用方法

### 快速安装

```shell
( PKGVER=20230221 PKGREL=1 PKGFILN=pacman-mirrors-cn-${PKGVER}-${PKGREL}-any.pkg.tar.zst ; curl -L -o ${TMP}/${PKGFILN} https://github.com/ieu/msys2-mirrors-cn/releases/download/${PKGVER}-${PKGREL}/${PKGFILN} && pacman -U --needed --noconfirm ${TMP}/${PKGFILN} ; ( [ -f ${TMP}/${PKGFILN} ] && rm ${TMP}/${PKGFILN} ) )
```

### 使用预构建软件包

1. 从 [release page](https://github.com/ieu/msys2-mirrors-cn/releases) 下载软件包

2. 使用 `pacman` 安装软件包

```shell
pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar.zst
```

3. 开始使用

```shell
pacman -Syu
```

### 手动设置

1. 下载所需镜像列表文件并保存至 `/etc/pacman.d/`

2. 编辑 `/etc/pacman.conf`，参考以下配置添加上述镜像列表文件：

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

使用 `sed` 可快速添加镜像列表文件

```shell
sed -i -e '/^\[\(clangarm64\|mingw32\|mingw64\|ucrt64\|clang32\|clang64\)\]$/a Include = \/etc\/pacman.d\/mirrorlist.mingw.cn' -e '/^\[msys\]$/a Include = \/etc\/pacman.d\/mirrorlist.msys.cn' /etc/pacman.conf
```

4. 开始使用

```shell
pacman -Syu
```

## 从源码构建软件包

1. 安装 toolchain

```shell
pacman -S binutils
```

2. 克隆代码

```shell
git clone https://github.com/ieu/msys2-mirrors-cn.git
```

3. 打包

```shell
makepkg
```

## 收录站点

* [北京外国语大学开源软件镜像站](https://mirrors.bfsu.edu.cn/)
* [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)
* [中国科学技术大学开源软件镜像](https://mirrors.ustc.edu.cn/)
* [南京大学开源镜像站](https://mirrors.nju.edu.cn/)
* [哈尔滨工业大学开源镜像站](https://mirrors.hit.edu.cn/)
* [上海交通大学 Linux 用户组软件源镜像服务](https://mirrors.sjtug.sjtu.edu.cn/)
* [北京理工大学开源软件镜像服务](https://mirrors.bit.edu.cn/)
* [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror/)
* [中国科学院软件研究所开源镜像站](https://mirror.iscas.ac.cn/)
* [腾讯软件源](https://mirrors.cloud.tencent.com/)