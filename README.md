# USBShutdown

--

# Install

    sudo apt install python-gobject python3-gobject python-gi python3-gi python-pyudev python3-pyudev

# Setup 

To setup the USB of your choice when unplugged to safe shutdown your device run the following:

    sudo python unplug2shutdown.py --configure

It will ask to plug the desired USB device(which can be almost anything even a printer)
into any available USB port. 

It will ask you to confirm, finish the prompts and done!

It will then create a ".usbshutdownrc" in your home directory such as "/home/pi/" or "/root/"

# System Auto Start - shortly will have an option to add this as a service!

Lastly lets make the tool startup with the system so it actually works!

Run the following to edit the needed startup file:

    sudo nano /etc/rc.local

Next, add the below above the last line which is "exit 0"

    /home/dir/usbshutdown.py&

**The "&" is very important, make sure it is there at the end of the line before saving**

# Remove USB Shutdown - are you sure?

This is the easiest part, of course, first remove the following 2 files:

    sudo rm /home/dir/usbshutdown.py .unplug2shutdownrc

Next to remove the startup line added, either comment out or remove the line added into /etc/rc.local:

    OLD!
    sudo nano /etc/rc.local
    /home/dir/unplug2shutdown.py&

    NEW!
    update-rc.d -f usbshutdown remove

IT HAS BEEN REMOVED!
