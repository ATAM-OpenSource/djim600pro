# DJI-M600-PRO
This project is about controlling dji matrice 600 pro drone with raspberry pi with data from laser tracker.
- Drone Information;
  - Model: DJI Matrice 600 Pro
  - Firmware Version: V1.00.01.67
  - For Drone Website -> https://www.dji.com/matrice600-pro
- OSDK Information;
  - Version: 3.9
  - A3, N3, M100, M210 V1, M600 and M600 Pro only support OSDK 3.9, and this version will continue to keep the basic maintenance.
  - OSDK Download Link -> https://terra-1-g.djicdn.com/71a7d383e71a4fb8887a310eb746b47f/osdk/OSDK-3.9.0.zip
- Raspberry Pi Information:
  - Model: Raspberry Pi 4 Model B 8GB Ram
  - Platform: RasPiOS 2023-05-03
  - C ++ compiler: GCC 5.4.0/5.5.0 version
  - CMake: 2.8 and above
  - Linux: Ubuntu 16.04 (If you need to use advanced sensor functions, please use the Libusb library)
  - Development Environment Information-> https://developer.dji.com/onboard-sdk/documentation/quickstart/development-environment.html
- USB-UART Converter Information
  - Model:CP2102 USB UART Board



In home/dji-osdk-3.9
```
sudo mkdir build
cd build
cmake ..
make

``` 
In home/dji-osdk-3.9/buid/osdk-core 
dji osdk library should be copied to raspberry pi library.
```
sudo cp libdjiosdk-core.a /usr/lib/
```

In home/dji-osdk-3.9/sample/platform/linux
```
sudo mkdir build
cd build
cmake ..
make
``` 
Creating UserConfig.txt to home/dji-osdk-3.9/sample/platform/linux all samples.

app_id:          //Developer ID\
app_key:         //App Key\
device:          //Serial port number\
bauderate:       //Serial baud rate\
acm_port:        //ACM port number


device /dev/ttyUSB0\
baudrate 115200\
acm port usually /dev/dev/ttyACM0

from https://account.dji.com/login?appId=dji_sdk&backUrl=https%3A%2F%2Fdeveloper.dji.com%2Fuser&locale=en_US 

The following is execute the "Flight Control": 
```
./djiosdk-flightcontrol-sample UserConfig.txt UserConfig.txt
```
```
 █████╗ ████████╗ █████╗ ███╗   ███╗
██╔══██╗╚══██╔══╝██╔══██╗████╗ ████║
███████║   ██║   ███████║██╔████╔██║
██╔══██║   ██║   ██╔══██║██║╚██╔╝██║
██║  ██║   ██║   ██║  ██║██║ ╚═╝ ██║
╚═╝  ╚═╝   ╚═╝   ╚═╝  ╚═╝╚═╝     ╚═╝
                                    


```