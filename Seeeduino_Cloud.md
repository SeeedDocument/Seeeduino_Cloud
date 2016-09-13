#Seeeduino Cloud
--------
##Introduction

![](https://github.com/SeeedDocument/Seeeduino_Cloud/blob/master/images/seeeduino_cloud_cover.jpg?raw=true)

Seeeduino Cloud is a microcontroller board based on [Dragino WiFi IoT module HE](http://www.dragino.com/products/linux-module/item/87-he.html) and ATmega32u4. HE is a high performance, low cost 150M, 2.4G WiFi module which means “core” in Chinese and with an Open Source OpenWrt system inside. Seeeduino Cloud is also an Arduino compatible board, 100% compatible to Grove, shield and IDEs(Arduino IDE 1.5.3 and later). Except for the normal interface of Arduino, Seeeduino Cloud has built-in Ethernet and WiFi support, a USB-A port which makes it very suitable for those prototype design that need network connection and mass storage. It is also a good idea to make Seeeduino Cloud to be an IoT gateway.

##Application Ideas

* Internet of Things  
* Smart House
* Learning 

We are looking forward to your interesting projects!

|Simple Wi-Fi Messager|Send data to Google Docs|Solar Panel Monitoring System|
|--------|----------|---------|
|![](https://cdn.instructables.com/FC3/FOVR/HQVLC501/FC3FOVRHQVLC501.MEDIUM.jpg)|![](https://cdn.instructables.com/FEK/CKBT/HO7XFET3/FEKCKBTHO7XFET3.MEDIUM.jpg)|![](https://cdn.instructables.com/FQI/J0IT/IIDJEIC0/FQIJ0ITIIDJEIC0.MEDIUM.jpg)|
|[Make it Now](http://www.instructables.com/id/Arduino-Yun-Messager/)|[Make it Now](http://www.instructables.com/id/Google-Docs-and-the-Arduino-Y%C3%BAn/)|[Make it Now](http://www.instructables.com/id/Arduino-Yun-Solar-Panel-Monitoring-System/)|


##Features

* Compatible with Arduino Yun
* Based on Dragino WiFi IoT module HE
* Open Source OpenWrt system inside
* Support 2.4Ghz WiFi, 802.11 b/g/n
* Support Ethernet
* Support USB 2.0
* On-board Grove connectors

##Specification

Because Seeeduino Cloud has two processors, this section shows the characteristics of each one in two separate tables. 

###Dragino HE Module
|Parameter|Value|
|------------|------------|
|CPU|ATHEROS AR9331|
|Clock Speed|400MHz|
|RAM|64MB|
|Flash|16MB|
|OS|OpenWrt|
|Interfaces|2 x RJ45, 1 x USB Host, 1 x UART, 14 multiplex GPIOs|
|Power|3.3V Power Input|
|WiFi|Support 150M 2.4Ghz WiFi, 802.11 b/g/n|

###AVR Arduino Microcontroller

|Parameter|Value|
|------------|-------------|
|Microcontroller|ATmega32u4|
|Flash Memory|32KB|
|SRAM|2.5kB|
|EEPROM|1kB|
|Clock Speed|16MHz|
|Operating Voltage|5V|
|Digital I/O Pins|20|
|PWM Channels|7|
|Analog Input Channels|12|

##Hardware Overview

The images below show an overview of Seeeduino Cloud hardware features. The pin-out and alternate functions of various pins of Seeeduino Cloud are shown in the pin-out diagram. This could be used as a quick reference.

![](https://github.com/SeeedDocument/Seeeduino_Cloud/blob/master/images/seeeduino_cloud_hardware.png?raw=true)
  

* **RJ45 Ethernet Port**
The LAN Port is connected to ATHEROS AR9331 and has its own IP address that can be used for Internet connection and device management.
* **USB Input**
USB Port is used to connect the board to your PC for programming and for powering up. Micro USB is the ubiquitous version of USB, found in most Android phones, and other devices. You probably have dozens of these cables laying around your house.
* **USB HOST**
Seeeduino Cloud provides USB host capability that enables it to connect to various USB devices such as webcams, USB drives, keyboards, joysticks and more.
* **32U4 RST**
Pressing the 32U4 Reset button will reset the ATmega32U4 MCU. Usually, it is used for re-starting your sketch. 
* **SYS RST**
Pressing the System Reset button will reboot the Linux system. 
* **Wi-Fi RST**
The Wi-Fi Reset button only supports long press. When pressed and released after 5 seconds, it will reset the WiFi settings. Other settings will be retained. If the button is pressed and released after 30 seconds, it will reset ALL the settings to factory default. 
* **Grove Connectors**
SeeedStudio has a variety of sensors/devices that can make use of this I2C or UART connection. In addition, we sell independent Grove connectors to help you make our own sensor connections. The I2C Grove connector is also connected to analog pin A4 and A5 for SDA and SCL respectively if you would like to use those pins instead. The UART Grove connector is connected to digital pins 0 and 1 for RX and TX respectively.
* **ICSP**
This is the ICSP connection for the ATmega32U4, it is located in the standard ICSP/SPI position for Arduino Uno, Due, Mega, and Leonardo compatible hardware (e.g. shields) that may use this connector. The SPI pins in this port: MISO, SCK, and MOSI, are also connected to digital pins 12, 13, and 11 respectively just like those of the Arduino Uno.
* **I-PEX Connector**
This is an I-PEX Connector for an external antenna.
* **Pins**
It is not possible to access the I/O pins of the Atheros AR9331. All I/O lines are tied to the ATmega32U4. 


##Getting Started

Seeeduino Cloud has two processors on board. One is an ATmega32U4 like on the Leonardo. The other is an Atheros 9331, running Linux and the OpenWRT wireless stack, which enables the board to connect to WiFi and Ethernet networks. With [Yun Bridge Library](https://www.arduino.cc/en/Reference/YunBridgeLibrary), it is possible to call programs or custom scripts on the Linux system through the Arduino to connect with various internet services.


###Program on ATmega32U4 side
    
The ATmega32U4 is programmed using the [Arduino Software (IDE)](https://www.arduino.cc/en/Main/Software?setlang=en), if you haven't install, please click [here](https://www.arduino.cc/en/Guide/HomePage) for installation instructions.
    
####Install the Driver

First of all, you need to:

* **Get a Micro-USB cable**
    * You need a Micro-USB cable first; the data cable of an Android Phone will do fine.
If you can't find one, you can buy one [here](http://www.seeedstudio.com/depot/Micro-USB-Cable-48cm-p-1475.html?cPath=98_100).

!!!Warning
    Take gentle care in handling micro USB socket, or you might break the socket off.

* **Connect the board**
    * The Seeeduino Cloud automatically draw power from either the USB connection to the computer or an external power supply. Connect the Arduino board to your computer using the USB cable. The green power LED (labelled **PWR**) should go on.

#####For Windows
Windows version of Arduino Software (IDE) already contains the proper drivers. When you installed it you let the operating system install them. Connect your Seeeduino Cloud and the drivers will be installed automatically.

#####For MAC
The first time you plug a Seeeduino Cloud into a Mac, the "Keyboard Setup Assistant" will launch. There's nothing to configure with the Seeeduino Cloud; you can close this dialogue by clicking the red button in the top left of the window.

#####For Linux
There is no need to install drivers for Ubuntu 10.0.4 and later, but make sure port 5353 is not being blocked by a firewall.

####Open your first sketch

Open the LED blink example sketch: File > Examples >01.Basics > Blink.

![](https://www.arduino.cc/en/uploads/Guide/UNO_Load_Blink.jpg)

####Select your board type and port

You'll need to select the entry in the Tools > Board menu that corresponds to your Arduino or Genuino board.

![](https://www.arduino.cc/en/uploads/Guide/YUN_SelBoard.jpg)

Select the serial device of the board from the Tools | Serial Port menu. This is likely to be COM3 or higher (COM1 and COM2 are usually reserved for hardware serial ports). To find out, you can disconnect your board and re-open the menu; the entry that disappears should be the Arduino or Genuino board. Reconnect the board and select that serial port. When your board is properly configured on WiFi, you will find it in the Port list, as in our screenshot.

![](https://www.arduino.cc/en/uploads/Guide/YUN_SelPort.jpg)

####Upload the program

Now, simply click the "Upload" button in the environment. Wait a few seconds - you should see the RX and TX leds on the board flashing. If the upload is successful, the message "Done uploading." will appear in the status bar.

![](https://www.arduino.cc/en/uploads/Guide/UNO_Upload.png)

A few seconds after the upload finishes, you should see the LED(D13) on the board start to blink (in green). If it does, congratulations! You’ve gotten Arduino up-and-running. If you have problems, please see the troubleshooting suggestions.

###Program on ATHEROS AR9331 side

####Configure Network

The Seeeduino Cloud has a WiFi interface and a LAN port. Either of them has IP address that can be used for internet connection and device management.

#####Wi-Fi AP Mode
When you power ON the Seeeduino Cloud for the first time, there will be an unsecure WiFi network called SeeeduinoCloud-AXXXX shown in wifi connections.
You can connect your computer to this network as shown below. Your computer will get an ip of this network **192.168.240.xxx**. The Seeeduino Cloud has a default ip address of **192.168.240.1**.

#####Wi-Fi STA Mode
After connect SeeeduinoCloud-AXXXX, type 172.31.255.254 or 192.168.240.1 in browser search box and you will connect to Seeeduino Cloud with web UI. The default password is "seeeduino", then click LOG IN.
Click "SYSTEM", select your Wi-Fi network, enter the password and click "CONFIGURE & RESTART". 

![]()

#####Onboard Ethernet
When you connect Seeeduino Cloud to a wired network with an ethernet cable, it will try to connect automatically via DHCP. The board will show up on the ports menu just as it would over WiFi.


####Terminal
You could access the terminal of Seeeduino Cloud via SSH to Program or configure on ATHEROS AR9331 side.
* Download a SSH client such as [putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
* Use the IP address of Seeeduino Cloud and run SSH client.
* ```
username: root
password: seeeduino
```

![]()

####



#####Yun Bridge Library

#####Update Firmware  

#####IoT Server Configuration
The IoT Server page allows you to upload data to IoT websites such as Xively while you only need to write sensor data to serial port.

![]()

and the sketch is shown below. 

```
/*
  Simulate UART TX Data 
 
 This sketch simulate Temperature and Humidity data to UART. 
 
 To test the pass through feature for different IoT service 
 
 created 25 Apr 2014
 by Dragino Technology Co., Limited
 
 Reference:
 http://wiki.dragino.com/index.php?title=Xively#Upload_data_to_Xively_use_Pass_Through_Mode
 
 */
String dataString = "";
 
void setup() {
  Serial1.begin(115200);
}
 
void loop() {
  dataString = "temp:";
  dataString += random(10) + 20;
  Serial1.println(dataString);  // upload Temperature data
  delay(20000);
  dataString = "humidity:";
  dataString += random(5) + 70;  // upload humidity data
  Serial1.println(dataString);  
  delay(20000);
}
```

##Resources

* **Schematic**
    * [Seeeduino Lotus Eagle file](
    
    
##FAQ

* What is the difference between Seeeduino CLoud and LinkIt Smart 7688 DUO?


##Help us to make it better