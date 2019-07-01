# Raspberry-Pi

Get the toolchains from [https://github.com/raspberrypi/tools](https://github.com/raspberrypi/tools). This repository contains multiple toolchains. The one that is known to work is `tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf`.

Clone the RPi tools repository:
```
cd $HOME
mkdir git
cd git
git clone https://github.com/raspberrypi/tools
```

Create a staging directory for installation files, for example `mkdir $HOME/rpi_staging`.

## CryptoPP library

The [cryptopp library](https://github.com/bartslinger/cryptopp) can be compiled for RPi as follows:

```
cd $HOME/git
git clone https://github.com/bartslinger/cryptopp.git
cd cryptopp
export ARM_EMBEDDED_TOOLCHAIN=$HOME/git/tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin
export ARM_EMBEDDED_SYSROOT=$HOME/git/tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/arm-linux-gnueabihf
source ./setenv-rpi.sh
make -f GNUmakefile-cross
```

## OpenSSL

The following commands will install the openSSL library files in $HOME/rpi_staging.

```
cd $HOME/git
git clone https://github.com/openssl/openssl
cd openssl
export PATH=$HOME/git/tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin:$PATH
./configure linux-generic32 --prefix=$HOME/rpi_staging
make CC=arm-linux-gnueabihf-gcc
make install
```