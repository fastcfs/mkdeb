# mkdeb
make deb package

```
清理源代码树(debian/rules clean)
构建源代码包(dpkg-source -b)
构建程序(debian/rules build)
构建二进制包(fakeroot debian/rules binary)
制作 .dsc 文件
用 dpkg-genchanges 命令制作 .changes 文件。
```

```
对于非本土 Debian 软件包，比如 gentoo， 构建软件包之后，你将会在上一级目录(~/gentoo) 中看到下列文件：
gentoo_0.9.12.orig.tar.gz
这是原始的源代码 tarball，最初由 dh_make -f ../gentoo-0.9.12.tar.gz 命令创建，它的内容与上游 tarball 相同，仅被重命名以符合 Debian 的标准。

gentoo_0.9.12-1.dsc
这是一个从 control 文件生成的源代码概要，可被 dpkg-source(1) 程序解包。

gentoo_0.9.12-1.debian.tar.gz
这个压缩的 Tar 归档包含你的 debian 目录内容。其他所有对于源代码的修改都由 quilt 补丁存储于 debian/patches 中。
如果其他人想要重新构建你的软件包，他们可以使用以上三个文件很容易地完成。只需复制三个文件，再运行 dpkg-source -x gentoo_0.9.12-1.dsc。 [64]

gentoo_0.9.12-1_i386.deb
这是你的二进制包，可以使用 dpkg 程序安装或卸载它，就像其他软件包一样。

gentoo_0.9.12-1_i386.changes
这个文件描述了当前修订版本软件包中的全部变更，它被 Debian FTP 仓库维护程序用于安装二进制和源代码包。它是部分从 changelog 和 .dsc 文件生成的。
```

```shell script
rpm -ql libfastcommon
/usr/lib64/libfastcommon.so
```

```
/home/fastcfs/git/libfastcommon-1.0.50
/home/fastcfs/git/libfastcommon-1.0.50/debian
```

```shell script
https://www.debian.org/doc/manuals/debian-faq/pkg-basics.zh-cn.html#:~:text=A%20Debian%20%22package%22%2C%20or%20a%20Debian%20archive%20file%2C,format%20are%20described%20in%20the%20deb%285%29%20manual%20page.
https://unix.stackexchange.com/questions/592349/how-to-include-and-install-debian-package-timer-file-inside-deblan-package-alon#
https://unix.stackexchange.com/questions/20554/how-to-include-data-files-pictures-text-files-in-a-debian-package
https://linuxconfig.org/easy-way-to-create-a-debian-package-and-local-package-repository
https://debian-handbook.info/browse/stable/sect.building-first-package.html

https://packages.debian.org/stretch/amd64/lightning/filelist
https://wiki.debian.org/Packaging/Intro
https://wiki.debian.org/BuildingAPackage

https://www.debian.org/doc/manuals/maint-guide/build.zh-cn.html
```

```shell script
https://mentors.debian.net/intro-maintainers/
```