{\rtf1\ansi\ansicpg1252\cocoartf1404\cocoasubrtf470
{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
\margl1440\margr1440\vieww10800\viewh8400\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 VNC is a helpful tool to the Raspberry Pi project, and can help with troubleshooting or other similar issues. To install VNC in Raspbian, open up a terminal window and enter the following:\
\
``` \
sudo apt-get install tightvncserver\
tightvncserver\
```\
	At this point, you will be prompted to enter a password. If it is longer than 8 characters, it will be truncated to 8.  Check to ensure you can log in to the VNC server on your Pi by using the VNC viewer software for your platform. Start a connection with pi.local:5901. 5901 is the default port, and pi.local is your Pi\'92s IP address, obtainable through entering ```ifconfig``` in the terminal.\
\
When you reboot your Pi you will have to start VNC again. To avoid this, have it start at boot. Enter the following:\
\
```\
sudo nano /etc/init.d/vncboot\
```\
Then, add the following to the file:\
\
```\
#!/bin/bash\
sudo tightvncserver\
```\
ctrl+x, y, enter\
\
```\
sudo chmod 755 /etc/init.d/vncboot\
sudo update-rc.d vncboot defaults\
```\
\
}