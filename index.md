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
1. Download Ubuntu or a similar Linux system: [Ubuntu Desktop](https://ubuntu.com/download/desktop).
2. Enable Hyper-V in Windows: [Enable Hyper-V on Windows](https://docs.microsoft.com/en-US/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v). (Check that your processor supports virtualization and it's enabled in the BIOS).
3. Create a virtual machine (VM) on Windows: [Setup a virtual machine with Hyper-V](https://docs.microsoft.com/en-US/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine).
4. Install the dependencies:
	* [GNU Make >= 3.81](https://www.gnu.org/software/make/) --> In Ubuntu: `sudo apt-get install make`
	* [Libevent >= 2.0](http://libevent.org/) --> In Ubuntu: `sudo apt-get install libevent-dev`
	* [pkg-config](https://www.freedesktop.org/wiki/Software/pkg-config/) --> In Ubuntu: `sudo apt-get install pkg-config`
	* [OpenSSL >= 1.0.1](https://www.openssl.org/) --> In Ubuntu: `sudo apt-get install openssl`
	* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) --> In Ubuntu: `sudo apt-get install git-all`
	* [libtoolize](https://manpages.debian.org/stretch/libtool/libtoolize.1.en.html) --> In Ubuntu: `sudo apt-get install libtool`
	* [gcc-mingw-w64](http://mingw-w64.org/doku.php) --> In Ubuntu: `sudo apt-get install gcc-mingw-w64`
	* [mingw-w64](http://mingw-w64.org/doku.php) --> In Ubuntu: `sudo apt-get install mingw-w64`
	* [libssl-dev](https://packages.debian.org/de/jessie/libssl-dev) --> In Ubuntu: `sudo apt-get install libssl-dev`
	* [autoconf](https://www.gnu.org/software/autoconf/) --> In Ubuntu: `sudo apt-get install autoconf`
	* [automake](https://www.gnu.org/software/automake/) --> In Ubuntu: `sudo apt-get install automake`
	* [libtool](https://www.gnu.org/software/libtool/) --> In Ubuntu: `sudo apt-get install libtool`
	* [pandoc](https://pandoc.org/) --> In Ubuntu: `sudo apt-get install pandoc`
	
	--> All together:
	
	```bash
	sudo apt-get install make libevent-dev kg-config openssl git-all libtool gcc-mingw-w64 mingw-w64 libssl-dev autoconf automake libtool pandoc
	```
	
5. Download the git repository from github: 
```bash
git clone https://github.com/pgbouncer/pgbouncer.git
cd pgbouncer
git submodule init
git submodule update
```

6. Compile for Windows using:
```bash
./autogen.sh
./configure --host=i686--w64-mingw32 ...
make
```

## Further links
* [https://www.pgbouncer.org/](https://www.pgbouncer.org/)
* [https://github.com/pgbouncer/pgbouncer](https://github.com/pgbouncer/pgbouncer)
* [https://www.pgbouncer.org/install.html#building-on-windows](https://www.pgbouncer.org/install.html#building-on-windows)
* [http://winpg.jp/~saito/pgbouncer/](http://winpg.jp/~saito/pgbouncer/)
* [https://stackoverflow.com/questions/37925410/how-to-install-pgbouncer-on-windows-7-x64](https://stackoverflow.com/questions/37925410/how-to-install-pgbouncer-on-windows-7-x64)
* [https://github.com/pgbouncer/pgbouncer/issues/442](https://github.com/pgbouncer/pgbouncer/issues/442)

Change history
--------------

* **Version 1.0.0.0 (2019-12-05)** : 1.0 release.
