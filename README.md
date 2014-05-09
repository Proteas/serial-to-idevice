Demo: Serial Communication Between iDevice and OS X
=========

Ref
--------------
http://devdot.wikispaces.com/Iphone+Serial+Port+Tutorial

http://pbxbook.com/other/mac-tty.html

https://github.com/armadsen/ORSSerialPort

http://www.prolific.com.tw/US/ShowProduct.aspx?p_id=229&pcid=41

Steps
--------------
1. check out the code: git clone --recursive https://github.com/Proteas/serial-to-idevice.git

2. download and install the driver: md_PL2303_MacOSX-10.6up_v1.5.1.zip

3. after rebooting your mac, unload the driver with: sudo kextunload /System/Library/Extensions/ProlificUsbSerial.kext

4. go to dir "/System/Library/Extensions/ProlificUsbSerial.kext", edit Info.plist, add your device's vendor id and product id

5. load the driver: sudo kextload /System/Library/Extensions/ProlificUsbSerial.kext

6. ls /dev/tty.usb*, you will find: /dev/tty.usbserial, then the driver is successly loaded.

7. got to dir "app-idevice", exe make, then you got "serial-echo"

8. copy "serial-echo" to your idevice, and exe it.

9. open project "ORSSerialPort/Examples/CocoaDemo/ORSSerialPortCocoaDemo.xcodeproj", and run it.

10. select "usbserial", and open it. first, send: *, and your device got a connection, then send: A, or somthing else.
