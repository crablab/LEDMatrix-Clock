# LED Matrix Clock
This is a couple of bash scripts to display the time/date on your LED matrix controlled by a Raspberry Pi.
You can get the matricies from Adafruit as well as the HAT to control them. 

##Installation
The library utilises [/hzeller/rpi-rgb-led-matrix](https://github.com/hzeller/rpi-rgb-led-matrix) and you can find instructions to install it on the repository page. 

The scripts are designed to run on 4 chained matricies - you can edit this by modifying the `-c` parameter - you will have to change the font size and alignment. Colour is provided by passing the `-C` parameter and uses a standard RGB structure (ie. white would be `-C255, 255, 255`. `-y` and `-x` are used to modify the y-axis and x-axis offsets respectivly. 

The .sh files _must_ be in the same directory as `text-example` in the `rpi-rgb-led-matrix` directory. 

##Running the script
Elevated access is required to run the script, thus `sudo` is used. 
`sudo time.sh` will display the time
`sudo date.sh` will display the current date

If you want to keep the script running for any legnth of time it is recommended you either run the script in a Tmux session or create a cron job.

In order to create a cron job run `sudo crontab -e` - a sample crontab is provided:
`@reboot cd /home/pi/led-matrix/; bash time.sh` - note, you must be in the same directory as the bash script (and thus the library) when the script is executed. 

Feel free to add any issues and comments - I will do my best to help. 
