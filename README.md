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

If you need to stop the cron job first identify the PID with `top -p $(pgrep -d',' bash)` (it will generally be the one using most system resources and/or running the longest) then `kill xxxx` where xxxx is replaced with the PID. If it doesn't work, try another of the PID's listed! 

##Examples
Time: 
![alt text](https://lh3.googleusercontent.com/K7uVjOE9c_CRsIHhj6qMEHtCSWiL7OfyYwpzFtkOucrII_MvVIecGtlqZoNFx6ZfS5Wlcd_RxakuMluKmNpmEr_3FgHjwyFxXQliI5gfMvcpjUwNgNgndxx4w1Zwmwc-WDU5M-1EGHdZzxvwPmJ4JPFSIQ6RSPfIyVTqCpvBPLnazyQGLsG2vw2sa7csRAT2aX8glP2gZKhUesxu_Tkl7SZNHEhsQSnvZvj2cgVzv7o2IPyc90VTZU5w2IYFTDin44gfX5-0lLlHfivsy_r59k-Xqeq_Gi9LCTvmZNLjVrq5wWP5ZBP-SyjC2fQoDkR9xpS-O9RtfYPmM4Fy3S_mrIkhSpdfYBaDw0tbckcF2lNk0Xu_CDx7MCCPVq38M3iBSYO0W-VyMmBy8zHtvlBgc9i2WSkD1wqmFjqqNk_oHJgzgRxQxaBCGnQwQlVTSOQ-iSW4VXjmF7o7nGONiMqmPxpV6KfzmQsWfvKd9-yCNlI7xM87HhOyA3L57_WZIHScqvdwM9h89yZs7EtrvKLTCXEPL3v7NLKXImamq9cTPTY9VN6PXG1UyCEJoipnZvkOVgkPFhLbMmqXfuIqUifhwZJXNxik-0p7JreYsv62NWA7b7xXEA=w1920-h603-no "time")
Date:
_coming soon..._

Feel free to add any issues and comments - I will do my best to help. 
