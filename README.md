### File list
* /usr/src/sys/arch/arm/nxp/imx6_clk.c
* /usr/src/sys/arch/arm/nxp/imx6_iomux.c

### Boot log
https://dmesgd.nycbug.org/index.cgi?do=view&id=8171

### Build kernel
./build.sh -U -u -O /usr/builds/obj.earmv7hf -T /usr/builds/tool.earmv7hf -j2 -m evbarm -a earmv7hf kernel=GENERIC

### Write image
dd if=armv7.img of=/dev/rld0d bs=1m conv=sync

### U-Boot
cd /usr/pkgsrc/sysutils/u-boot-riotboard ; make install
dd if=/usr/pkg/share/u-boot/riotboard/u-boot.imx of=/dev/rld0d bs=1k seek=1 conv=sync
