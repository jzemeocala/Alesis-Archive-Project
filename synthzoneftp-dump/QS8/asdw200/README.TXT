ALESIS SERIAL PORT WINDOWS MIDI DRIVER
version: 2.00
========================================================
This driver and oemsetup are located in \ALESIS\ASDWIN\
This driver is used to send and receive midi data to and from your QS6,
QS7, or QS8 via the synthesizer's serial port connection.
See your QS owner's manual for more info on the serial port.
To install this driver, see the following instructions for the version
of Windows you are using.  Be sure to read the Notes below regarding
parameter settings of the Driver.

Sections of this document
(1) Installation of the Alesis Serial Port Windows Midi Driver
(2) Changing the driver parameters after installation
(3) The driver parameters
(4) Notes on Midi Input Persistance Parameter


*********************************************************
(1) INSTALLING THE ALESIS SERIAL PORT WINDOWS MIDI DRIVER
*********************************************************

SETUP FOR WINDOWS 3.1
=====================
-Open Control Panels
-open the drivers applet.
-select "Add"
-select "Unlisted or Updated driver"
-when prompted for a location of the driver,select browse
-navilgate to the appropriate disk locations for the 
 ASDWIN oemsetup info.
-Follow the Windows instructions.
-If you are upgrading your Alesis Serial driver, Windows
 may ask if you want to use the existing driver, in this
 case, select "new" so Windows will use the new driver.
-When the Alesis Serial driver applet appears, select the COM
 port that the QS synth is attached to.
-You will be asked to restart Windows for the new driver
 to take effect.


SETUP FOR WINDOWS 95
=====================
-Go to the Settings item in the Start Menu.
-Select the "Control Panel" item
-Select "Add New Hardware"
-Select "NO" (do NOT have windows auto-detect hardware)
-Select "Sound, Video, Game contollers" as hardware type. 
-When prompted for device, select "Have Disk"
-Navigate to the OEM setup in the ASDWIN directory
-Follow the Win95 instructions.
-If you are upgrading your Alesis Serial driver, Windows
 may ask if you want to use the existing driver, in this
 case, select "new" so Windows will use the new driver.
-When the Alesis Serial driver applet appears, select the COM
 port that the QS synth is attached to.
-You will be asked to restart Windows for the new driver
 to take effect.

*********************************************************
(2) CHANGING THE DRIVER PARAMETERS AFTER INSTALLATION
*********************************************************

LOCATING THE DRIVER IN WINDOWS 3.1
==================================
-Open Control Panels
-open the drivers applet
-select "Alesis Serial MIDI Driver" in the driver list
-select the "Setup" button
-now the Alesis Serial MIDI Driver Setup window is open
-for a description of the parameters, refer to the next
 section of this document.
-If you make changes to the driver you may be asked to
 restart Windows for the new driver settings to take effect.

LOCATING THE DRIVER IN WINDOWS '95
==================================
-Go to the Settings item in the Start Menu.
-Select the "Control Panel" item
-Select "Multimedia" to open the multimedia applet
-Select the "Advanced" tab
-Under "Midi Devices and Instruments" select
 the "Alesis Serial MIDI Driver Out"
-Select the "Properties" button
-Select the "Settings..." button
-now the Alesis Serial MIDI Driver Setup window is open
-for a description of the parameters, refer to the next
 section of this document.
-If you make changes to the driver you may be asked to
 restart Windows for the new driver settings to take effect.


*********************************************************
(3) THE DRIVER PARAMETERS
*********************************************************
*the driver setup parameters are identical in Windows 3.1
 and Windows '95.

THE MAIN SETUP WINDOW
=====================
-Serial Port Connection:
  This setting determines which of the available COM ports
  on your computer the driver will use to communicate with
  your QS serial port.  Select the port that is connected
  to your QS synth's serial port.  You may also disable
  the driver by setting it to "Disabled", this is useful
  if you need to disable the driver temporarily and don't
  want to remove it.  You may also set a custom address
  for your COM port, for info on this see the next part of
  this section: The Advanced Setup Window.

-Status:
  This part of the display shows which QS synth (if any) that
  the driver has currently established a connection with.
  If no connection has been made, the display will read:
  "Alesis synth not detected"

-Enable Status and Warning Messages:
  If this checkbox is turned ON (the default), you will be
  given status messages whenever a MIDI application initializes
  a connection to the Alesis Serial MIDI driver.
  This status message will let you know if connection has
  been made and the baud rate for the connection.  If no
  connection was made, an option will be given to retry.

-OK button
  By selecting the "OK" button, you are accepting the settings
  of the driver.  If you have made any changes, the new
  settings may not take effect until you restart Windows.

-CANCEL button
  By selecting the "Cancel" button, you will dismiss any
  changes made to the driver, in other words no changes
  will be made.

-ADVANCE button
  This enters you into the The Advanced Setup Window.  For
  more info on this window, see the next part of this section.

-ABOUT button
  This will display the current version of the driver, credits
  and copyright information.


THE ADVANCED SETUP WINDOW
=========================

-Use Custom IRQ/Address:
  Check this box if you need to setup a custom address for
  your computer's serial port.  If you don't know what this
  means you probably don't need to use it.

-Base I/O Address:
  The address setting of your computer's serial port.  This
  is only used if "Use Custom IRQ/Address" is on. (see above)

-IRQ:
  The interupt setting of your computer's serial port.  This
  is only used if "Use Custom IRQ/Address" is on. (see above)

-Current Link Baud Rate:
  This displays the current baud rate the Alesis Serial MIDI
  driver is using to communicate with the QS Synth.  If no
  connection was made to a QS synth, the driver will default
  to 38.4k baud.

-Speed Limit:
  This setting is where you select the top speed you want the
  Alesis Serial MIDI driver to communicate with the synth.
  If the driver detects a QS6, the speed limit will be limited
  to 38.4k since the QS6 is not capable of high speeds.  For
  the QS7 or QS8, the maximum speed limit is 115.2k.  If you
  are experiencing problems with high speed communication, you
  might try setting the driver with a lower speed limit.  
  Communication problems could be caused by a number of things,
  such as a poorly shielded serial cable, a slow computer,
  an old serial interface chip in your computer, etc.

-Input Persistance:
  This setting allows you to set the MIDI Input persistance
  value.  Basically, this sets the amount of time your
  computer should allocate to processing incoming MIDI
  data.  Unless you are sure of your setting, you should
  let the driver set the recommended value for you (next..)
  For detailed informatiion on this setting, see the next
  section: "Notes on Midi Input Persistance Parameter"

-Use Recommended Value button:
  This button will determine the best Input Persistance
  setting for your computer and serial interface chip.
  see "Input Persistance" above.

-OK button
  By selecting the "OK" button, you are accepting these
  advance settings for the driver.  If you have made any
  changes,  you must also select "OK" in the Main setup
  window for the changes to be recognized by the driver.
  the new settings may not take effect until you restart
  Windows.

-CANCEL button
  By selecting the "Cancel" button, you will dismiss any
  advanced changes made to the driver, in other words no
  changes will be made.


*********************************************************
(4) NOTES ON THE MIDI INPUT PERSISTANCE PARAMETER
*********************************************************
New for version 2.00
--------------------
If the Alesis Serial Port Windows driver detects a FIFO'd UART,
it will set the persistance value to 0 when you select "use recommended
value" in the advanced section of the driver setup.

Background
----------
Most PC's have either 8250, 16450 or 16550 UART chips installed as
their COM hardware.  8250 and 16450 UARTs do not have FIFOs built 
into them and therefore are unable to buffer incoming data at high 
speeds.  In layman's terms this means 8250- and 16450-based machines 
usually can not keep up with the speed requirements of MIDI and 
sometimes lose data, particularly when the machine is running Windows.
The 16550 UART, on the other hand, has a 16-byte FIFO built into it 
that enables it to queue up incoming data until the computer has time 
to process it.

The MIDI input persistance setting allows the Alesis Serial MIDI 
Driver to better handle the high rate of incoming MIDI data.
Basically, the higher the persistance setting, the more time the 
computer allows for handling the MIDI input data stream.  With 
the proper persistance setting, a system with non-16550 UARTs
will not drop incoming data.

How to set MIDI input persistance
---------------------------------
The parameter may be set via the Control Panel.  Run the "Drivers"
applet from the Control Panel, then select Alesis Serial MIDI driver.
When the Alesis driver dialog box appears, select "Advanced".  The
first time the driver is loaded, the machine will attempt to run an
auto-calibration and calculate a suggested persistance value.  You
may select the suggested value, or supply one of your own.  It is
usually best to use the recommended persistance value, but you may
want to set it lower if you already know you have a 16550 UART
installed, or if your system seems to be sluggish with the current
persistance setting.

Side-Effects of MIDI persistance
--------------------------------
Because the driver is trying to compensate in software for a hardware 
deficiency, you might notice several side-effects when running the 
driver with a high persistance setting.  During long System Exclusive 
(SYSEX) dumps from the synthesizer to the computer, it will appear 
that the system is no longer responding to keystrokes and mouse 
movements.  This is because the driver is consuming a great amount
of the processor's time while receiving data.  Once the SYSEX dump
is complete, the computer will again respond to keyboard and mouse
input.  If the persistance is set too high, the system will appear
sluggish whenever the synthesizer is transmitting data to the computer,
whether it's note on/off information, or some other event such as
the pitch wheel.  The secret is to set the persistance value to a
value high enough to not drop incoming data, but low enough to not
stall the machine in non-SYSEX situations.  If your computer is 
fast-enough (let's say 486DX4-100 or Pentium-class) you may be able 
to set a persistance value of 0.  If you have a 16550 UART installed 
in your system, you may also be able to set persistance to 0 with 
slower processors.

How to find out what UART you have
----------------------------------
The MSD (Microsoft Diagnostics) program exists on most PCs.  Run
MSD from the DOS prompt, then select "COM Ports..."   MSD will
list the currently installed UARTs and tell you what type they are.
Most computers come with 8250 or 16450 UARTs installed.  Some of
the more expensive models, ie Compaq, come with 16550 UARTs standard.
There are also add-in serial cards that have 16450 or 16550 UARTs
on them.
