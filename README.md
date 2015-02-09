# conkyChameleon
conkyChameleon is a bash script you can use to match Conky's window color with the Unity Launcher. Neat!
It also works with other desktop environments: Conky's color becomes the average color of the desktop background.

This script works best with transparent or translucent themes that use few to non estatic background images to represent the Conky UI (like the Glass, New-Minty, Transparent, and Ubuntu-Touch themes by Harmattan), and requires the use of an X-based window server. If you don't know what that means, you're probably fine. 

To use this script:

1. Download it.
2. Give it executable permissions. sudo chmod +x /path/to/conkyChameleon/script.
3. Change the ownership of the file to your user: chown you:you /path/to/conkyChameleon/script.
4. Directly edit your .conkyrc: Comment out own_window_transparent and uncomment own_window_argb_visual and own_window_argb_value.  Set your argb value to something between 0 and 255, 0 for transparent and 255 for opaque. I use 80 and it works fine. Create a new window specification called own_window_colour and set it to 000000.  conkyChameleon will overwrite this field when it updates your Conky's window color.
5. Create a cron job for it.  crontab -e will allow you to edit your crontab, which is the file that determines when cron jobs run--we're going to use it to set conkyChameleon to run in the background once a minute. Add SHELL=/bin/bash and PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/path/to/conkyChameleon at the beginning of the file. Then add * * * * * /path/to/conkyChameleon and @reboot /path/to/conkyChameleon to the end of the file. Make sure that the file has a newline at the end or it won't run(just a crontab idiosyncracy). 
6.  Enjoy!


In future versions I will update the script so that parts of this setup are done automatically.  I may also update it so that it is a modification to a .conkyrc.  We'll see.



