# zigbee-cc2531-flash
Tools &amp; manual for flashing CC2531 stick

original manual: https://github.com/itsmepetrov/homebridge-zigbee/blob/master/docs/Flashing.md

## Building for macOS

```bash
brew install libusb
brew install boost
brew install pkgconfig

git clone https://github.com/dashesy/cc-tool.git
cd cc-tool
autoconf
autoreconf -fvi
./configure
make
```

This repo contains prebuilt binary `cc-tool` for macOS.

## Flashing 

```bash
wget https://raw.githubusercontent.com/mtornblad/zstack-1.2.2a.44539/master/CC2531/CC2531ZNP-Pro-Secure_LinkKeyJoin.hex
./cc-tool -e -w CC2531ZNP-Pro-Secure_LinkKeyJoin.hex
```

This repo contains firmware file also.

## Further usage

- You need to get last [raspbian](https://www.raspberrypi.org/downloads/raspbian/).
- Create a microSD card with [etcher](https://www.balena.io/etcher/)
- Setup a HomeBridge with

```bash
sudo apt install git
git clone https://github.com/fantomnotabene/homebridge_setup_script
cd homebridge_setup_script
bash install.sh
```

- Login on :8080 with `admin:admin`
- Install ZigBee platform plugin for HomeBridge https://github.com/itsmepetrov/homebridge-zigbee#readme