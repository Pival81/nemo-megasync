# Nemo-MEGASync
A nemo port of the nautilus-megasync package. All I did was replace the word nautilus with nemo in every file of the tarball.

* [Requirements](#requirements)
* [Compile](#compile)
* [Uninstall](#uninstall)


## Requirements

Apart from Nemo and MEGASync, you require:

On Arch:
````
qt4
glib2
gnome-common
hicolor-icon-theme
````

On Fedora, CentOS and OpenSuSE:
````
qt-devel
glib2-devel
nemo-devel
gnome-common
libnemo-extension
hicolor-icon-theme
````

On Debian and Ubuntu:
````
cdbs
libqt4-dev
intltool
autotools-dev
libnemo-extension1
libgtk2.0-bin
libtool-bin
libtool
libnemo-extension-dev
````
## Compile

To install run these commands:
````
$ git clone https://github.com/Pival81/nemo-megasync.git
$ cd nemo-megasync
$ export DESKTOP_DESTDIR=/usr
````
Then, if you're running Fedora, CentOS, OpenSuSE or Arch:
````
$ qmake-qt4
````
or else:
````
$ qmake
````
And then the following commands:
````
$ make
$ sudo make install
$ sudo mkdir -p /lib64/nemo/extensions-3.0   #if you're on 32bit, replace lib64 with lib.
$ sudo install libMEGAShellExtNemo.so -D /lib64/nemo/extensions-3.0 ````   #if you're on 32bit, replace lib64 with lib.
$ sudo rm -fr /usr/share/icons/hicolor/icon-theme.cache
$ /bin/touch --no-create /usr/share/icons/hicolor &>/dev/null || :
````
Then you only have to restart nemo with ```` nemo -q ```` and reopen it again.

## Uninstall

To uninstall it, get back to the directory cloned with git and do:
````
$ sudo make uninstall
````
