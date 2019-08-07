# Raspberry-Pi

Get the toolchains from [https://github.com/raspberrypi/tools](https://github.com/raspberrypi/tools). This repository contains multiple toolchains. The one that is known to work is `tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf`.

```
cd $HOME
mkdir git
cd git
git clone https://github.com/raspberrypi/tools
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

## OpenVPN
This requires OpenSSL

```
cd $HOME/git
git clone --branch v2.4.7 https://github.com/OpenVPN/openvpn.git
cd openvpn
export PATH=$HOME/git/tools/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin:$PATH
./configure OPENSSL_LIBS="-L$HOME/rpi_staging/lib -lssl -lcrypt" \
LZO_LIBS="-L$HOME/rpi_staging/lib -llzo2" \
LZO_CFLAGS="-I$HOME/rpi_staging/include" \
--target=arm-linux-gnueabihf \
--host=arm-linux-gnueabihf \
--build=x86_64 \
--prefix=$HOME/rpi_staging \
--disable_plugins

make && make install
```
