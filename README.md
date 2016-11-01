# LED Matrix Clock
This is a couple of bash scripts to display the time/date on your LED matrix controlled by a Raspberry Pi.
You can get the matricies from Adafruit as well as the HAT to control them. 

##Installation
The library utilises [/hzeller/rpi-rgb-led-matrix](https://github.com/hzeller/rpi-rgb-led-matrix) and you can find instructions to install it on the repository page. 

The scripts are designed to run on 4 chained matricies - you can edit this by modifying the `-c` parameter - you will have to change the font size and alignment. Colour is provided by passing the `-C` parameter and uses a standard RGB structure (ie. white would be `-C255, 255, 255`. `-y` and `-x` are used to modify the y-axis and x-axis offsets respectivly. 
