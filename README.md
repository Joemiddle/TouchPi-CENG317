# This is a project to develope a communicator that between Pis sends morse messages for a college project

##Table of Contents
1. [Introduction] Intro to Project
2. [Cost] Cost to reproduce project
3. [Time] Estimate of Time commitment to reproduce
4. [Assembly] Assembly
5. [Configuration] Configuring the Pi
6. [Run] How to make it run

![Image of Prototype](https://github.com/Joemiddle/TouchPi-CENG317/blob/master/documentation/PartsPic.jpg)

### Cost

The cost of this project varies, its possible to do this project with a single rasperry pi
however the full functionallity is designed for two.

Here's what you'll need

PiTFT plus 320x240 3.2"     cost $39.95CAD
Canakit Rapbery PI 3 complete Starter Kit 32 GB edition    cost $99.99CAD
Eisco Labs Contact Key, Telegraphing/Morse Code, Single    cost $9.77CAD

toatl cost after taxes   $169.18CAD(338.34)

Other thing's you'll need

Some wire and cutters
soldering iron and solder (Don't forget your saftey glasses)
jumper wires
two cables with an aligator clip on one end and a banana clip on the other 
Keyboard, (No mouse required the touch screen handles that well)
And last but not least if you are trying to connect the two raspberry pis you'll need a
internet connection.



###Time

This project shouldn't take more than a few days assuming every day half an hour to 
and hour is spent

### Assembly

Assembly of the project is fairly straight forward however some soldering is required.
WARNING purchasing the pitft as a kit will require some more soldering, here is a link
that will assist in guiding you through that.
https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/assembly


1. So if you noticed the touch screen had 8 component holes, here you'll need to solder
   wire, or what I suggest clipping part of a resistor and soldering two of those into 
   the component holes labeled with #27 on the bottom right. Note be careful with soldering 
   these leads on as if you heat the component hole too much it is possible to damage
   the touch screen, speaking out of personal experience here.

2. after the component has cooled down connect jumper wires to the two pins, then connect
   the aligator clip to the one end of the jumper (some wire required first) and then the
   banana clip fits perfectly to the Eisco Contact Key.

3. Next part is simple you only need to connect the touch screen to the raspberry pi
   the screen should fit over top of the pi in a way that if covers the pi, If the screen
   looks like it hangs off the bottom of the pi you have the screen upside down so turn it
   around and plug it in again. If any of the pins of the touch screen is not connected
   it is not connected correctly make sure all pins are connected and the orientation 
   of the screen is correct.


   Here is what it should look like
![Build Image](https://github.com/Joemiddle/TouchPi-CENG317/blob/master/documentation/BuildPic.JPG)


### Configuration

   Before plugging in the sd card that comes with the raspberry pi there are some steps that 
   need to completed before testing things out.

1. first step is image the raspberry pi, in order to do this download the image here
   <https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/easy-install

2. if you have software to burn an image on the an sd card you can skip this step.
   after you have downloaded the image you'll need to be able to burn it onto the sd card
   some software is required. Etcher is the softare that I used to burn the image onto my sd
   card, however if you have other software you can use that but for those who don't here is 
   the link to download Etcher, after downloading go ahead an install
   https://etcher.io/

3. if your sd card is formatted to exFat or you can format it yourself to exFat skip 
   this skep.
   Etcher is fortunately fairly simple to use however before just running it and burning
   the image you'll need to make sure the sd is formatted to exFAT there is software somewhere
   out there in the internet here is a link to what I used, download and install and format 
   your sd card to exFat
   <https://www.sdcard.org/downloads/formatter_4/

4. Now after the SD formatter is installed, connect the sd card with the sd card reader 
   that comes in the raspberry pi kit. Make sure that when using the formatter to format
   the sd card to verify that is formated to exFat or the card may can fail to have the
   imaged burned to it.

5. After formatting the sd card next is to use Etcher to burn the image to the card, and
   back to the point I made two steps ago, Etcher is failry straight forward to use.
   First you select the image that you will burn, this will be the file unzipped that was
   obtained in step 1 after selecting the image, next make sure you select your sd card.
   The last thing to do here is to click Flash!, this will take a while so you might as 
   well go make some tea or whatever.

6. Now you can plug in the raspberry pi and start it up. If the pitft display displays
   bright white and remains in that state for longer than 5 minutes its possible something
   has gone wrong with the installation, if that is the case verify that you have installed
   the correct image and restart the process.

7. Now that the Raspberry pi has started there are a few things you'll need to do. First
   you need to go the Raspberry pi configuration. To navigate to it you can click on the 
   start menu -> Preferences -> Raspberry Pi Configuration, while in here you'll want to
   change a few things set up for the pi. In the system tab you can chnage your password
   and host name for your raspberry pi(This is a saftey option).Next go to the Interfaces
   tab, in here you will want to enable SSH , VNC , PSI, and I2C. SSH and VNC are just
   to allow you to use other tools in order to access the PI remotely, I will be going 
   over the SSH use but the VNC use isn't necessary.

8. Now that your Pi is configured you need to get the software to run everything, here 
   are a few options of how you can get that done. After getting an internet connection
   on the raspberry Pi you can navigate to its internet browser and go to 
   <https://github.com/Joemiddle/TouchPi-CENG317/tree/master/software
   here you will see three important python files(They are the ones that end in .py)
   download them all on the raspberry pi. After downloading them to the raspberry pi
   you can move them from the downloads folder to another folder at your own discression
   However for ease of use I suggest making a folder in the root of the user and then 
   runing the python code in that folder. The other way of getting these files onto the
   raspberry pi is the putty way on your computer not the pi. first download and run putty
   link below
   <http://www.putty.org/
   after you download putty you'll still need to establish an internet connection on the 
   pi. Now on the Pi you need to go to the a terminal window by clicking on the start 
   menu-> Accessories -> Terminal. Once in the terminal type in ifconfig which will 
   let you find the ip address of the raspberry pi, if you are connecting to a local 
   private network it will probably be something along the lines of 192.168.0. 1 to 255
   after that you will type that into putty as the Host Name (or IP address) and click
   open at the bottom it will prompt you for username / password so make sure you know it
   if you left it as the default it will be pi / raspberry.  Now on your computer you will
   want to open the python files in notepad or notepad++. Copy the content of the file
   and paste it into the same file name, you can make a file and start editing it with 
   the command sudo nano (filename).
   so and example of it is to copy the content of the file clientCode.py and then on the 
   pi create that file and start editing it with "sudo nano clientCode.py" all in one line.
   Now you just paste what you copied from clientCode.py to save you can press CRL + X 
   and then y and then enter. Repeat this process for all the files codeServer.py and
   tcpmorse_lookup.py. Now the Pi should be ready.

9. This step is the longest process... You've got to configure the second raspberry pi,
   the fortunate part to this part is you've done it all before, after you've finished 
   the second pi you're done setting everything up and its onto testing.


   ###Run

  To run you need to the ifconfig on both of the pis in order to get their ips, make sure
  to make a note of it. Now you need to make one pi the server and the other the client,
  it doesn't matter which one is which but you need to type in different commands for each
 
  The server needs to run its command first
  sudo python3 ./codeServer.py

  The client can then run its code with this command
  sudo python3 ./clientCode.py


  After that both screen should display ready and if both have correclty connected you will
  be able to send a message to the other pi by typing in morse. the pi you send the message
  on will be able to hear the morse however the won't see the message, the message will 
  display on the other pi. And with that its done!

  I hope you've may of learned a bit about the Raspberry Pi running through this process
  or maybe a bit if you've looked at the python code however thats all folks!









