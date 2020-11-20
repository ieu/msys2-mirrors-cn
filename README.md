MSYS2 中国镜像站

## 使用方法

1. 下载[镜像包](https://github.com/ieu/msys2-mirrors-cn/releases)

2. 安装软件包

```shell
# pacman -U pacman-mirrors-cn-${pkgver}-${pkgrel}-any.pkg.tar
```

3. 编辑 `/etc/pacman.conf` 在原镜像列表前添加镜像文件 `/etc/pacman.d/mirrorlist.{mingw{32,64},msys}.cn`

示例：
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

一行编辑命令（使用 `sed`）：
```shell
sed -i 's/^\[\(mingw32\|mingw64\|msys\)\]$/\0\nInclude = \/etc\/pacman.d\/mirrorlist.\1.cn/' /etc/pacman.conf
```

4. 开始使用

```shell
# pacman -Syu
```

## 从源代码打包

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
$ cd msys2-mirrors-cn
$ makepkg -c
```

## 收录站点

* [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)
* [中国科学技术大学开源软件镜像](https://mirrors.ustc.edu.cn/)
* [北京理工大学开源软件镜像服务](https://mirror.bit.edu.cn/)
* [北京外国语大学开源软件镜像站](https://mirrors.bfsu.edu.cn/)
* [上海交通大学 Linux 用户组 软件源镜像服务](https://mirrors.sjtug.sjtu.edu.cn/)
* [南京大学开源镜像站](https://mirrors.nju.edu.cn/)
* [华为开源镜像站](https://mirrors.huaweicloud.com/)
* [腾讯软件源](https://mirrors.cloud.tencent.com/)