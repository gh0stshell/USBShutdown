# USBShutdown

Version 2 of the original project unplug2shutdown. Upgraded imports, code, and added features such as install the service to auto run the script instead of having to manually add it to your system which used the same script for both so now there is a separate file just for auto run.

# Install Dependancies

    sudo apt install python-gobject python3-gobject python-gi python3-gi python-pyudev python3-pyudev

# Setup 

To setup the USB of your choice when unplugged to safe shutdown your device run the following:

    sudo python unplug2shutdown.py --configure

It will ask to plug the desired USB device(which can be almost anything even a printer)
into any available USB port. 

It will ask you to confirm the device plugged in, finish the prompts and done!

It will then create a ".usbshutdownrc" in your home directory such as "/home/pi/" or "/root/"

# System Auto Start

Lastly lets make the tool startup with the system so it actually works!

**Old Way - manually add line to system startup file

Run the following to edit the needed startup file:

    sudo nano /etc/rc.local

Next, add the below above the last line which is "exit 0"

    /home/dir/usbshutdown.py&
    
**New way - script will auto install usbShutdown service file

--Coming Soon!

**The "&" is very important, make sure it is there at the end of the line before saving**

# Remove USB Shutdown - are you sure?

This is the easiest part, of course, first remove the following 2 files:

    sudo rm /home/dir/usbshutdown.py
    sudo rm .unplug2shutdownrc

Next to remove the startup line added, either comment out or remove the line added into /etc/rc.local:

   **OLD Manual Way
    
    sudo nano /etc/rc.local
    
  **Remove the following line or comment the line out with a #
    
    /home/dir/unplug2shutdown.py&

IT HAS BEEN REMOVED! :(

