# WiringPiE 


This is a fork of the unofficial mirror/fork of the wiringPi library to control GPIO pins on the Raspberry Pi.

- [wiringPi unofficial mirror on GitHub.](https://github.com/WiringPi)
- [Gordon Henderson's wiringPi page.](http://wiringpi.com/)

This fork of wiringPi has a few modifications from the original:

- Support for devices using the PCA9685 PWM controller, such as the Adafruit motor and servo hats,  is included using Reinhard Sprung's code.
- A few additional methods are added to support get and set of PWM controller properties
- All functions that setup an I2C, SPI, or serial port device return the file descriptor on success or -1 for error.
- A simple logging framework with a callback function is implemented so you monitor and display logs in  your program code.
- Program error handling is modified; original wiringPi would exit on non fatal errors, now it will log an error message and return NULL or -1 to let the program handle it.

The goal for creating this modified version of wiringPi is to have code that can run on either Raspberry Pi or NVIDIA Jetson Nano with minimal modification.


  
