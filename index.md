PgBouncerWinBinaries
====================================

PgBouncerWinBinaries is a project to host pre-built Windows binaries of the [pgBouncer](https://www.pgbouncer.org/) project.

[![Build status](https://ci.appveyor.com/api/projects/status/502wxfe78xcfihm9?svg=true)](https://ci.appveyor.com/project/SeppPenner/pgbouncerwinbinaries)
[![GitHub issues](https://img.shields.io/github/issues/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/issues)
[![GitHub forks](https://img.shields.io/github/forks/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/network)
[![GitHub stars](https://img.shields.io/github/stars/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/SeppPenner/PgBouncerWinBinaries/master/License.txt)
[![Gitter](https://badges.gitter.im/PgBouncerWinBinaries/community.svg)](https://gitter.im/PgBouncerWinBinaries/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Still work in progress, there is an error at the moment: Check [this issue](https://github.com/pgbouncer/pgbouncer/issues/442) on Github.

## Downloads built by me:
* 1.12.0: [Download](/Downloads/pgbouncer-1.12.0-win-x64.zip)

## Downloads from Saito:
* 1.12.0: [Download](/Downloads_Saito/pgbouncer-1.12.0-win-x64.zip)
* 1.9.0: [Download](/Downloads_Saito/pgbouncer-1.9.0-win32.zip)
* 1.8.1: [Download](/Downloads_Saito/pgbouncer-1.8.1-win32.zip)
* 1.7.2: [Download](/Downloads_Saito/pgbouncer-1.7.2-win32.zip)
* 1.7.1: [Download](/Downloads_Saito/pgbouncer-1.7.1-win32.zip)
* 1.6.1: [Download](/Downloads_Saito/pgbouncer-1.6.1-win32.zip)
* 1.5.5: [Download](/Downloads_Saito/pgbouncer-1.5.5-win32.zip)
* 1.5.4: [Download](/Downloads_Saito/pgbouncer-1.5.4-win32.zip)
* 1.5.3: [Download](/Downloads_Saito/pgbouncer-1.5.3-win32.zip)
* 1.5.2: [Download](/Downloads_Saito/pgbouncer-1.5.2-win32.zip)
* 1.5.0: [Download](/Downloads_Saito/pgbouncer-1.5-win32.zip)
* 1.4.2: [Download](/Downloads_Saito/pgbouncer-1.4.2-win32.zip)
* 1.4.0: [Download](/Downloads_Saito/pgbouncer-1.4-win32.zip)
* 1.3.4: [Download](/Downloads_Saito/pgbouncer-1.3.4-win32.zip)
* 1.3.3: [Download](/Downloads_Saito/pgbouncer-1.3.3-win32.zip)

## How to build your own binary
1. Create a folder like `C:\PGBouncerForBuilding`. Don't use special chars or empty spaces or stuff like that.
2. Download and install [MSYS2](https://www.msys2.org/).
3. Update the package database and core system packages with: `pacman -Syu`
4. If needed, close MSYS2, run it again from Start menu. Update the rest with: `pacman -Su`
5. Install the needed packages:

    ```bash
    pacman -S msys/libtool
	pacman -S msys/libevent
    pacman -S msys/autoconf
    pacman -S msys/automake-wrapper
	pacman -S msys/pkg-config
	pacman -S base-devel gcc cmake
	pacman -S msys/libevent-devel
	# Not sure if these are really needed:
	pacman -S mingw-w64-x86_64-libevent
    pacman -S mingw-w64-x86_64-pkg-config
    pacman -S mingw-w64-x86_64-gcc
    ```
	
6. If you get the error: `configure: error: no acceptable C compiler found in $PATH`, you need to do:
    * Install build toools using `pacman -S --needed base-devel mingw-w64-i686-toolchain mingw-w64-x86_64-toolchain git subversion mercurial mingw-w64-i686-cmake mingw-w64-x86_64-cmake`
    * Add `C:\msys64\mingw64\bin` and `C:\msys64\mingw32\bin`, in that order, to your PATH variable.
	* Note that MSYS2 also puts a lot of other tools in this directory, most notably Python. So put these entries below any other tools you might have installed in your PATH.

7. Go to your root folder, e.g. `C:\PGBouncerForBuilding`.
8. Clone the git repository to your folder using:

    ```bash
    git clone https://github.com/pgbouncer/pgbouncer.git
    cd pgbouncer
    git submodule init
    git submodule update
    ```

9. Compile for Windows using:

    ```bash
    ./autogen.sh
    ./configure ...
    make
    make install
    ```

## Further links
* [https://www.pgbouncer.org/](https://www.pgbouncer.org/)
* [https://github.com/pgbouncer/pgbouncer](https://github.com/pgbouncer/pgbouncer)
* [https://www.pgbouncer.org/install.html#building-on-windows](https://www.pgbouncer.org/install.html#building-on-windows)
* ~~[http://winpg.jp/~saito/pgbouncer/](http://winpg.jp/~saito/pgbouncer/)~~
* [https://stackoverflow.com/questions/37925410/how-to-install-pgbouncer-on-windows-7-x64](https://stackoverflow.com/questions/37925410/how-to-install-pgbouncer-on-windows-7-x64)
* [https://www.msys2.org/](https://www.msys2.org/)
* [https://github.com/pgbouncer/pgbouncer/issues/442](https://github.com/pgbouncer/pgbouncer/issues/442)
* [https://osdn.net/projects/mingw/ticket/39946](https://osdn.net/projects/mingw/ticket/39946)
* [https://stackoverflow.com/questions/26453293/what-is-the-best-way-to-install-pkg-config-on-mingw-in-2014](https://stackoverflow.com/questions/26453293/what-is-the-best-way-to-install-pkg-config-on-mingw-in-2014)
* [https://stackoverflow.com/questions/37725825/aclocal-not-found-for-mingw-sh-autogen-sh-execution](https://stackoverflow.com/questions/37725825/aclocal-not-found-for-mingw-sh-autogen-sh-execution)
* [https://github.com/orlp/dev-on-windows/wiki/Installing-GCC--&-MSYS2](https://github.com/orlp/dev-on-windows/wiki/Installing-GCC--&-MSYS2)
* [https://feaforall.com/install-c-language-gcc-compiler-windows/](https://feaforall.com/install-c-language-gcc-compiler-windows/)
* [https://stackoverflow.com/questions/33398574/cant-compile-pgbouncer-neither-in-linux-nor-in-windows](https://stackoverflow.com/questions/33398574/cant-compile-pgbouncer-neither-in-linux-nor-in-windows)

## Further links (Not so relevant)
* [https://www.aerospike.com/docs/client/libevent/build/windows.html](https://www.aerospike.com/docs/client/libevent/build/windows.html)
* [https://github.com/libevent/libevent/releases/](https://github.com/libevent/libevent/releases/)
* [https://www.quora.com/What-are-some-ways-of-installing-libevent](https://www.quora.com/What-are-some-ways-of-installing-libevent)
* [https://stackoverflow.com/questions/1710922/how-to-install-pkg-config-in-windows](https://stackoverflow.com/questions/1710922/how-to-install-pkg-config-in-windows)

Change history
--------------

* **Version 1.0.0.1 (2020-03-19)** : Updated build description.
* **Version 1.0.0.1 (2020-02-27)** : Updated description.
* **Version 1.0.0.0 (2019-12-05)** : 1.0 release.
