# cb2-v4-devboard
Tips and tricks how to use Whatsminer M20 H3 (CB2-V4) control board with generic Linux (Armbian)

# What can we do with it ?
Board have 2 I2C ports, analog audio output (need to solder wires), 4 UARTS (1 for console, other not tested yet), and 1 USB host.
So we can load Armbian from MicroSD card and play music, control external I2C, UART devices.
Board have 4 cores CPU Allwinner H3, 256 Mb RAM, 256 Mb NAND (?). Not very powerful, but now it can be cost for few $.

# Lets start!
1. Download Armbian image for Orange Pi PC Plus (maybe other will work too, but I don't want waste so much time for this)
2. Write it to card (BalenaEtcher, dd, etc)
3. Insert card in board, power on device
4. Now you can search device in your LAN and connect via SSH or connect directly to board via console UART pins
5. After creating users, entering password and other, install and run armbian-config
6. In armbian-config go to system->hardware and select: analog audio, i2c0, i2c1, i2c2, usbhost0,1,2,3

# Pinout
- 3 pin connector (line PC Fan connector) have address i2c2
- 3 connectors to hash boards have same I2C bus with address i2c0
- 4 holes near Flash - USB
- 2 small circles near CPU bottom - analog audio
  
![IMG_20240917_025436](https://github.com/user-attachments/assets/2730045b-e5b3-4ed8-a639-077973e3fed5)

Hash connectors pinout

![image](https://github.com/user-attachments/assets/c526de43-335e-497a-acf8-281298556ced)

# Proof of concept
Connected SSD1306 I2C LCD show uptime, IP, and other stuff:
![photo_5425141846809632964_y](https://github.com/user-attachments/assets/970009f7-efbf-47e5-84a2-b8b978a3c003)

Connected USB Flash drive to board:
![photo_5426883060911169441_y](https://github.com/user-attachments/assets/4dba3b18-bf89-4205-a77f-4c123a5c12ac)
![Снимок экрана 2024-09-18 000635](https://github.com/user-attachments/assets/be9f63e5-d855-4049-bc09-93af4fbb101e)

# Useful links
- https://github.com/andrejrcarvalho/OrangePi_SSD1306/tree/main
- https://linux-sunxi.org/images/4/4b/Allwinner_H3_Datasheet_V1.2.pdf
- https://github.com/zhaolei/WiringOP
