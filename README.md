# st-link-linux-64

git clone https://github.com/texane/stlink stlink.git
cd stlink.git
cmake .
make
#install binaries:
sudo cp st-* /usr/local/bin
sudo cp libstlink.* /usr/lib

#install udev rules
sudo cp etc/udev/rules.d/49-stlinkv* /etc/udev/rules.d/
#and restart udev
sudo restart udev

#-----------------------------------------------------------------------
convert hex-to-bin
arm-none-eabi-objcopy -I ihex --output-target=binary code00.hex code00.bin

./st-flash write stm-test.hex 0x8000000
#-----------------------------------------------------------------------

apt install libusb-dev
apt install autoconf
apt install libusb-1.0
