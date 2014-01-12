HID USB host demo for STM32F4 Discovery board

I have ported the STM3240G-EVAL board demo on Discovery board with GNU tools ARM embedded gcc 4.7 2012-q4 + makefile.
I've used STM32's work :
https://my.st.com/public/STe2ecommunities/mcu/Lists/STM32Discovery/Flat.aspx?RootFolder=%2Fpublic%2FSTe2ecommunities%2Fmcu%2FLists%2FSTM32Discovery%2FHID%20USB%20HOST%20example%20ported%20to%20STM32F4%20Discovery%20Mouse%20%2B%20KeyBoard&FolderCTID=0x01200200770978C69A1141439FE559EB459D75800084C20D8867EAD444A5987D47BE638E0F&currentviews=370

Initial text from "STM32" :
For people who are interested by connecting a mouse or a keyboard to the STM32F4 Discovery :
I have ported from the example provided in "USB On-The-Go host and device library" that works on STM3240G-EVAL board.
IAR 6.40 is used to compile the project. I didn't port it to other toolchains: keil, Tasking ...

When a mouse is connected:
The Blue Led should turn on.. Otherwise, desconnect the mouse or push the RESET button.
Clicking on the Left button of the mouse the green LED toggles
Clicking on the right button of the mouse the Red LED toggles
Clicking on the middle button of the mouse the orange LED toggles
moving the mose toggle the blue LED
Disconnecting the mouse from the Discovery board turns off all LEDs

When a Keyboard is connected:
The Blue Led should turn on.. Otherwise, desconnect the mouse or push the RESET button.
Hitting any key on the keyboard toggles the orange LED.
Disconnecting the mouse from the Discovery board turns off all LEDs

The port is done by:
Modifying the clock configuration: HSE clock from 25Mhz to 8Mhz
Removing all related LCD functions.
Configuring LEDs for the Discovery board. 
Deleting the polling on the user button in order to launch the HID application without waiting on user key press.

*******
This seems to work only with USB 2.0 mice and keyboards...

*******
update 2013-12-1: Basic Keil ARM MDK 4.70 environment added
