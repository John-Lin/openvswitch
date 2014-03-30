openvswitch
===========

UPDATE: Works now with OpenWrt "Barrier Breaker" (Bleeding Edge)

Open vSwitch 2.1.0 (OvS) package for OpenWrt

Installation
------------

Install this as a feed!

### Installation in OpenWrt

$ cd $TOPDIR
 
$ echo 'src-git openvswitch git://github.com/ttsubo/openvswitch.git' >> feeds.conf

$ ./scripts/feeds update openvswitch

$ ./scripts/feeds install -a -p openvswitch

$ make menuconfig

CONFIG_PACKAGE_kmod-crypto-crc32c=y  
CONFIG_PACKAGE_kmod-lib-crc32c=y  
CONFIG_PACKAGE_kmod-openvswitch=m  
CONFIG_PACKAGE_openvswitch-common=m  
CONFIG_PACKAGE_openvswitch-switch=m  

Edit .config
Comment Out "CONFIG_USE_MIPS16=y"

Edit package/libs/toolchain/Makefile
(http://patchwork.openwrt.org/patch/5019/)

$ make V=s
