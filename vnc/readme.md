VNC is a helpful tool to the TinyPi project, and can help with troubleshooting or other similar issues. To install VNC in Raspbian, open up a terminal window and enter the following:

``` 
sudo apt-get install tightvncserver
tightvncserver
```
	At this point, you will be prompted to enter a password. If it is longer than 8 characters, it will be truncated to 8.  Check to ensure you can log in to the VNC server on your Pi by using the VNC viewer software for your platform. Start a connection with pi.local:5901. 5901 is the default port, and pi.local is your Pi’s IP address, obtainable through entering ```ifconfig``` in the terminal.

When you reboot your Pi you will have to start VNC again by entering “tightvncserver” into the command line. To avoid this, have it start at boot. Enter the following:

```
sudo nano /etc/init.d/vncboot
```
Then, add the following to the file:

```
#!/bin/bash
sudo tightvncserver
```
ctrl+x, y, enter

```
sudo chmod 755 /etc/init.d/vncboot
sudo update-rc.d vncboot defaults
```

