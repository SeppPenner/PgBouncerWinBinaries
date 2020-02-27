PgBouncerWinBinaries
====================================

PgBouncerWinBinaries is a project to host pre-built Windows binaries of the [pgBouncer](https://www.pgbouncer.org/) project.
The page can be viewed under [https://sepppenner.github.io/PgBouncerWinBinaries/](https://sepppenner.github.io/PgBouncerWinBinaries/).

[![Build status](https://ci.appveyor.com/api/projects/status/502wxfe78xcfihm9?svg=true)](https://ci.appveyor.com/project/SeppPenner/pgbouncerwinbinaries)
[![GitHub issues](https://img.shields.io/github/issues/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/issues)
[![GitHub forks](https://img.shields.io/github/forks/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/network)
[![GitHub stars](https://img.shields.io/github/stars/SeppPenner/PgBouncerWinBinaries.svg)](https://github.com/SeppPenner/PgBouncerWinBinaries/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/SeppPenner/PgBouncerWinBinaries/master/License.txt)
[![Gitter](https://badges.gitter.im/PgBouncerWinBinaries/community.svg)](https://gitter.im/PgBouncerWinBinaries/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Still work in progress, there is an error at the moment: Check [this issue](https://github.com/pgbouncer/pgbouncer/issues/442) on Github.

## Downloads
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
2. Download and install [MinGW](http://www.mingw.org/).
3. In the MinGW installation manager install all packages (You can only install the relevant ones listed under [https://www.pgbouncer.org/install.html](https://www.pgbouncer.org/install.html), but this didn't work for me.
4. Open the MinGW shell.
5. Eventually you need to install libevent manually:
    * Download latest version from [https://github.com/libevent/libevent/releases/](https://github.com/libevent/libevent/releases/).
    * Unzip it and go to the libevent folder. e.g. `C:\PGBouncerForBuilding\libevent-2.1.11-stable`.
    * Compile and install it:

```bash
./configure
make
make install && make clean
```

6. Go to your root folder, e.g. `C:\PGBouncerForBuilding`.
7. Clone the git repository to your folder using:

```bash
git clone https://github.com/pgbouncer/pgbouncer.git
cd pgbouncer
git submodule init
git submodule update
```

8. Compile for Windows using:

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
* [https://github.com/pgbouncer/pgbouncer/issues/442](https://github.com/pgbouncer/pgbouncer/issues/442)
* [https://osdn.net/projects/mingw/ticket/39946](https://osdn.net/projects/mingw/ticket/39946)
* [https://www.aerospike.com/docs/client/libevent/build/windows.html](https://www.aerospike.com/docs/client/libevent/build/windows.html)
* [https://github.com/libevent/libevent/releases/](https://github.com/libevent/libevent/releases/)
* [https://www.quora.com/What-are-some-ways-of-installing-libevent](https://www.quora.com/What-are-some-ways-of-installing-libevent)

Change history
--------------

* **Version 1.0.0.1 (2020-02-27)** : Updated description.
* **Version 1.0.0.0 (2019-12-05)** : 1.0 release.
