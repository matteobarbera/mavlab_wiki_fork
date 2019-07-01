# Raspberry-Pi

Get the toolchains from [https://github.com/raspberrypi/tools](https://github.com/raspberrypi/tools). This repository contains multiple toolchains. The one that is known to work is `tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf`.

## CryptoPP library

The [cryptopp library](https://github.com/bartslinger/cryptopp) can be compiled for RPi as follows:

```
git clone https://github.com/bartslinger/cryptopp.git
cd cryptopp
export ARM_EMBEDDED_TOOLCHAIN=/path/to/tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin
export ARM_EMBEDDED_SYSROOT=/path/to/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/arm-linux-gnueabihf
source ./setenv-rpi.sh
make -f GNUmakefile-cross
```