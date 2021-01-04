# raspicam
Simple Python Script to use the Raspberry Pi Camera from Webbrowser

# Requirements
You should have installed Raspian and connected the Raspberry Pi Camera, the camera should also be enabled. 

# Installation
To get the scritp up and running do the following
```
sudo -H apt install python3-picamera
sudo apt install python3-pip
sudo -H pip3 install --upgrade picamera[array]
```
Try to run the the script by using this command (implies that the raspicam.py script is in the homefolder of the pi user):
```
sudo python3 /home/pi/raspicam.py
```

Then edit the rc.local file to start the script, if the pi starts.
```
sudo vi /etc/rc.local
```

In the file add this to the end, but before the last line exit 0
```
sudo python3 /home/pi/raspicam.py &

exit 0
```
Open the browser and type in the IP of your pi with port 8000, you should now see the camera :)

# Additional change IP Address
Open the dhcpcd config file and add e.g. this:
```
sudo vi /etc/dhcpcd.conf
```

```
interface wlan0
static ip_address=192.168.178.220/24
static routers=192.168.178.1
static domain_name_servers=192.168.178.1
```
