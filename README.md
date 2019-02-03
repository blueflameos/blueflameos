# blueflameos

# Requires 

Fedora 64bit.

20 GB Free Space In Root Partition.




# Build Version 30 rawhide

* sudo dnf install mock

* sudo usermod -a -G mock $USER

Logout/Login.




* mock -r fedora-30-x86_64 --init

* mock -r fedora-30-x86_64 --install lorax-lmc-novirt vim-minimal pykickstart git

open /etc/mock/site-defaults.cfg And Set config_opts['rpmbuild_networking'] to True .
* sudo vi /etc/mock/site-defaults.cfg




If Selinux Enforcing.
* sudo setenforce 0




* mock -r fedora-30-x86_64 --shell --old-chroot

* cd /home

* git clone https://github.com/blueflameos/blue-flame-os-kickstart

* cd blue-flame-os-kickstart



For Gnome on xorg Default Session.
* livemedia-creator --ks flat-blueflameos-live-workstation-xorg.ks --no-virt --resultdir /var/lmc --project BlueFlameOS-Workstation-Live --make-iso --volid BlueFlameOS-Workstation-30 --iso-only --iso-name BlueFlameOS-Workstation-Live-30-x86_64.iso --releasever 30 --title BlueFlameOS-Workstation-Live --macboot 



For Gnome Wayland Default Session.
* livemedia-creator --ks flat-blueflameos-live-workstation.ks --no-virt --resultdir /var/lmc --project BlueFlameOS-Workstation-Live --make-iso --volid BlueFlameOS-Workstation-30 --iso-only --iso-name BlueFlameOS-Workstation-Live-30-x86_64.iso --releasever 30 --title BlueFlameOS-Workstation-Live --macboot 




When Finish iso Saved in .
* ls /var/lib/mock/fedora-29-x86_64/root/var/lmc/BlueFlameOS-Workstation-Live-30-x86_64.iso 

