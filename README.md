# U-boot for Xiaomi Zigbee gateway with imx6 SoC DGNWG05LM, ZHWG11LM

## Install ARM Cross Compiler: GCC / Устанавливаем ARM Cross Compiler: GCC

* ### This is a pre-built (64bit) version of GCC that runs on generic linux, sorry (32bit) x86 users, it's time to upgrade... 
* ### Это предварительно собранная (64-битная) версия GCC, работающая на Linux.

### Download/Extract: / Скачиваем и распаковываем

```console
wget -c https://releases.linaro.org/components/toolchain/binaries/6.5-2018.12/arm-linux-gnueabihf/gcc-linaro-6.5.0-2018.12-x86_64_arm-linux-gnueabihf.tar.xz
tar xf gcc-linaro-6.5.0-2018.12-x86_64_arm-linux-gnueabihf.tar.xz
export CC=`pwd`/gcc-linaro-6.5.0-2018.12-x86_64_arm-linux-gnueabihf/bin/arm-linux-gnueabihf-
```
### Test Cross Compiler: / Проверяем что все установилось
```console
${CC}gcc --version

arm-linux-gnueabihf-gcc (Linaro GCC 6.5-2018.12) 6.5.0
Copyright (C) 2017 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```
### Clone u-boot from github and buid: / Клонируем u-boot с github и собираем

```console
git clone https://github.com/lmahmutov/uboot-imx-xiaomi.git
cd uboot-imx-xiaomi/
make ARCH=arm CROSS_COMPILE=${CC} distclean
make ARCH=arm CROSS_COMPILE=${CC} Xiaomi_defconfig
make menuconfig
make u-boot.imx  ARCH=arm CROSS_COMPILE=${CC}
```

 
