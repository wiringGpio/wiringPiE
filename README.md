# WiringPiE 


This is a fork of the unofficial mirror/fork of the original wiringPi library by Gordon Henderson, to whom we are grateful for creating arguably the best GPIO control code for the Raspberry Pi.

- [wiringPi unofficial mirror on GitHub.](https://github.com/WiringPi)
- [Gordon Henderson's wiringPi page.](http://wiringpi.com/)

This fork of wiringPi has a few modifications from the original:

- Support for PCA9685 PWM controller devices, such as the Adafruit motor and servo hats,  is built in using [Reinhard Sprung's code](https://github.com/Reinbert/pca9685).
- A few additional methods are added to support get and set PWM controller properties.
- Support for the second I2C bus on the Raspberry Pi (bus 0).
- All functions that setup an I2C, SPI, or serial port device return the file descriptor on success or -1 for error.
- A simple logging framework with a callback function is implemented so you can monitor and display logs in  your program code.
- Program error handling is modified; original wiringPi would exit on non fatal errors, this implementation will log an error message and return NULL or -1 to let the program handle it.

The goal for creating this modified version of wiringPi is for use with the wiringGpioExtensions library. The wiringGpioExtensions library allows you to write GPIO control code and build it for either Raspberry Pi or NVIDIA Jetson simply by changing the linker settings. It also provides some commonly used functions to control stepper motors, rotary encoders, seven segment displays, and more.

## Building
Use the build script to compile and install the library on your Pi.

```
$ chmod +x build
$ sudo ./build
```

If your Raspberry Pi OS does not use the expected directory layout, the build might fail with an error indicating the folders /usr/local/lib or /include are not found.  To fix this, run the following commands then try again.

```
$ sudo mkdir /usr/local
$ sudo mkdir /usr/local/lib
$ sudo mkdir /usr/local/include
```

To uninstall 
```
sudo ./build uninstall
```

To check your installation
```
$ gpio -v
```

  
