This is the LTS version of node.
Make sure to remove the latest node version package

Make sure following packages are installed:

```bash
   cards.devel c-ares icu python2 libuv
```

How to proceed:

## Open a terminal

## Create a new repository root directory:
```bash
   mkdir NuTyX-packages
```
##  Change to this directory
```bash
   cd NuTyX-packages
```
## Clone this package:
```bash
   git clone https://github.com/NuTyX-packages/node-lts.git
```
## Make sure you add the $PWD (in my example /hone/tnut/NuTyX-packages) directory in your /etc/cards.conf as new repository directiory 

```bash
# No global url should be defined
# We need to specify an url only for remote repositories collection
#
# Default global server URL 
# url http://downloads.nutyx.org
#
# My own repository (this repository) without specified url 
dir /home/tnut/NuTyX-packages
#
## For all the main desktops (KDE,XFCE,LXDE,MATE)
# Comment following line
# If you don't want to install any of those interfaces
#
dir /var/lib/pkg/depot/desktops|http://downloads.nutyx.org
#
## For all the graphical applications
dir /var/lib/pkg/depot/gui-extra|http://downloads.nutyx.org
#
## For a minimal graphical interface
dir /var/lib/pkg/depot/gui|http://downloads.nutyx.org
#
## For all the console applications
dir /var/lib/pkg/depot/cli-extra|http://downloads.nutyx.org
#
## For a minimal console interface
dir /var/lib/pkg/depot/cli|http://downloads.nutyx.org
#
## Chroot system without reboot possibilities for a chroot
dir /var/lib/pkg/depot/base|http://downloads.nutyx.org
#
## Normaly you want to keep base and
base /var/lib/pkg/depot/base
#
#
## If you want to keep more collections remove comments below
# Adjust to your needs
#
# base /var/lib/pkg/depot/cli
# base /var/lib/pkg/depot/cli-extra
# base /var/lib/pkg/depot//gui
# base /var/lib/pkg/depot/gui-extra
# base /var/lib/pkg/depot/...
```

### Notes that the global url is commented and a new url is specified for each remote repository.

## You are now ready to build, install and let cards been inform about this package:

```bash
   cd node-lts
   pkgmk -d -i
```

## To see if cards knows your package:

```bash
   cards info -b node-lts
   cards info node-lts
```

## Congratulations, you manage your first own package repository

