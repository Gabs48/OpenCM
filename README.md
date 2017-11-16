OPENCM
======

Makefile and tools to compile, upload and monitor a C project on a ROBOTIS OpenCM board.
It consists in a refactor of the following projects:
 - [Arduino-make](https://github.com/sudar/Arduino-Makefile)
 - The Robotis OpenCM projects ([compiled version](http://support.robotis.com/en/software/robotis_opencm/robotis_opencm.html), [source version (not maintained)](https://github.com/robotis-pandora/ROBOTIS-OpenCM)]

The repository contains the following folders:
  
  1. core : the core source and header files of the code that runs on the OpenCM platform
  2. examples : examples to show how to use the makefile and use the different functions of the board.
  3. hw : contains the firmware of the board, the 
  4. lib : useful libraries that can be used in the different OpenCM project to support external devices
  5. mk : the makefiles from Arduino-make modified for this specific refactor
  6. tools : a python script to upload code in the OpenCM boards as well as an arm toolchain to compile the sources


Create an OpenCM project
------------------------

Create a folder for your project with a .ino file containing the **setup()** and **loop()** functions. 
Copy the makefile from the example folder and set:

 - The **OPENCMIDE_DIR** variable only to point it to the location of this repository on your computer.
 - The **BOARD_TAG** to describe the hardware your are using (cm904, cm900 and cm900_rev10 should be supported but only cm904 has been tested).
 - The **MONITOR_PORT** that defines the USB device connected to the OpenCM board.

Compile the project
-------------------

In the project folder, simply execute:
```
make
```
To clean up, you can use:
```
make clean
```

Upload the project
------------------

Uploading the project can be done with the command (for unknown reason, my user does not have sufficient rights, so I use sudo here):
```
sudo make do_upload
```
It happens that the board do not repond. If it's the case, you can retry when pressing the *user_sw* button.

Serial Monitor
--------------

You can open the serial monitor via the make tool with:
```
make monitor
```


Other
-----

- Problem? Just add an issue on this github repository
- Using to QTcreator? Have a look here https://github.com/cleitonsouza01/qt-creator-arduino

 



