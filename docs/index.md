# Hacking the Renesas S5D9 IoT Fast Prototyping Kit

![](img/board/board-pmod.jpg)

## The Board and Tools

The board is incredible. It costs $35 and Renesas is currently
offering a [$20 coupon](http://learn.iotcommunity.io/t/s5d9-iot-fast-prototyping-kit-coupons-20-off/978), 
which reduces the cost to $15 plus shipping (from the factory in China). In addition to the
Renesas S5D9 MCU, you get a lot of onboard sensors:

- Bosch BMC 150 6-Axis sensor
- AMS ENS210 environmental sensor
- TE Connectivity MS5637-02BA03 barometric pressure sensor
- Knowles SPU0414HR5H-SB amplified SiSonic microphone

The board also has 3 colored LEDs plus Ethernet, USB, PMOD 2 Grove connectors and
a JTAG connector. 

Previous kits with this level of peripherals would have cost $150 6 months ago and 
$500 a few years ago. 

Renesas reduced costs by including sensors on the board and made
 several smart design trade-offs. These decisions made 
 the board even more attractive to hackers. At the current price of 
 $15 (after discount, but without
shipping), it's an astounding price drop and a compelling value.

The S5D9 kit does not come with these components:

- no LCD touchscreen (which is fine for most projects and you can add it's possible to hack one on later). The previous S3A7 kit
came with a New Haven 2.4" LCD. It made the board bigger and more expensive.
- no Segger debugger. The S3A7 kit came with a J-Link Lite Cortex-M 9-Pin debugger. The board comes with a bootloader. You can use a normal USB cable to load binaries on the board. 
- no USB or Ethernet cables. This is no problem as the cables are standard and cheap.

The board is economical way to learn Synergy, which is an amazing embedded development environment
for professionals. It's also a
great way to learn about cloud-based IoT systems like Renesas Data Monitoring (Bug Labs) and
Renesas Data Intelligence (Medium One).

The design files for the board are 
open sourced, enabling you to use the board design as a base to develop your own IoT device. 


