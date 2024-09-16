# cb2-v4-devboard
Tips and tricks how to use Whatsminer M20 H3 (CB2-V4) control board with generic Linux (Armbian)

# What can we do with it ?
Board have 2 I2C ports, analog audio output (need to solder wires), 4 UARTS (1 for console, other not tested yet), and maybe 1 USB host (not tested yet).
So we can load Armbian from MicroSD card and play music, control external I2C, UART devices.
Board have 4 cores CPU Allwinner H3, 256 Mb RAM, 256 Mb NAND (?). Not very powerful, but now it can be cost for few $.

# Lets start!
1. Download Armbian image for Orange Pi PC Plus (maybe other will work too, but I don't want waste so much time for this)
2. Write it to card (BalenaEtcher, dd, etc)
3. Insert card in board, power on device
4. Now you can search device in your LAN and connect via SSH or connect directly to board via console UART pins
5. After creating users, entering password and other, install and run armbian-config
6. In armbian-config go to system->hardware and select: analog audio, i2c0, i2c1, i2c2, usbhost0,1,2,3
