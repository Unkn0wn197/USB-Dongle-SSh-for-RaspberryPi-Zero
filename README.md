# USB-Dongle-SSh-for-RaspberryPi-Zero
Manual to install and configure the USB dongle for the RaspberryPi Zero

1.-Download the version you want from raspbian, I recommend the lite as it is the lightest.

2.-Mount the image using the BalenaEtcher program.

3.-Once mounted, go to the "boot" partition and edit the "config.txt" file by adding this "dtoverlay = dwc2" at the end.

4.-Now edit the file "cmdline.txt" by adding this "modules-load = dwc2, g_ether" right after the word "rootwait".

5.-Create a file without extension and call it "ssh".

6.-Remove the sd and place it in us RaspberryPi Zero.

7.-Now connect the USB dongle to your PC (with the RaspberryPi Zero already mounted).

8.-After a couple of minutes go to the equipment administration and there is look for your USB dongle, It is usually 
   in the ports section.(A trick to know what device it is, is to remove the USB Dongle and see which of the devices in 
   the administrator has disappeared).
   
9.-Once located we give you update driver, We look for driver software on this device and place the route where we 
   save the drivers downloaded from this github. This installs the RNDIS driver needed for the USB dongle, otherwise when 
   making the ssh connection it will tell you that the host does not exist.

10.-After doing this the device should appear in the network adapters section as RNDIS Gadget.

11.-If everything went well go to your cmd and place the command to perform the ssh taking into account that the host 
    is raspberrypi.local. It would look like this: "ssh pi@raspberrypi.local".
    
12.-If all went well, you should have an ssh connection with your RaspberryPi Zero.
