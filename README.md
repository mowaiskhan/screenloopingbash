# screenloopingbash
We had to loop screens of multiple applications for a business reason with a certain delay in Ubuntu Desktop. I have used wmctrl package to achieve this.


 Looper - This script will cycle through opened windows at any given point in time
           in Ubuntu Dekstop. It should work on any Linux provided wmctrl package
	    is available. You can open/close windows on runtime without disturbing
	    a running script and it will automatically pick newly opened applications 
 
 1) Download wmctrl package using following command
  sudo apt-get install wmctrl

 2) Open a terminal on Ubuntu/Linux and run following command
	this will list all windows opened right now, including
	your terminal which you are using
   wmctrl -l
owais@owais-virtual-machine:~$ wmctrl -l
0x02400003  0 owais-virtual-machine Mozilla Firefox
0x03a00007  0 owais-virtual-machine Ubuntu Software
0x03400007  0 owais-virtual-machine Image Viewer
0x0380000a  0 owais-virtual-machine owais@owais-virtual-machine: ~
 3)  Note hexadecimal window ID from first colum for your terminal
     here it is 0x0380000a 
 4) Open up script loop.sh from same terminal and modify 
     following variables
 TERMINAL_WINDOW_ID=0x0380000a <- Change it to your terminal id
 DELAY_IN_SWITCHING_WINDOWS_SECONDS=20 <- Change if you want to increase/decrease

 5) Launch script from this terminal as follows
     ./loop.sh

 6) Don't close this terminal else it will stop - Press CTRL+C to stop the script

 TIP: If you ever mess with your code in bash, download and shellcheck file.sh to know
 errors.


