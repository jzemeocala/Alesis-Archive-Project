___________________________________________________________________

                      Elan Digital Systems Limited.
___________________________________________________________________

Last Update    : 09/08/2002
Latest Release : V3-16
-------------------------------------------------------------------

	INSTALLATION NOTES
	------------------

	The MCE product is designed for Windows 95 and Windows 98.
	Windows Millennium is also supported (from issue 3-07).
	It will not work on Windows 3.x. 
	From issue 2-01 beta NT4 is also supported. 
	From issue 3-07 Windows 2000 is supported.
	From issue 3-13 XP is supported. 
	Two variants of MCE may now be obtained from Elan:
	* Memory Card Explorer ( 95/98/Me/NT4/2000/XP ) 
	* Memory Card Explorer ( 95/98/Me )

	Versions V3-15 and earlier
	Place install disk into drive a: and run 
	a:\setup.exe

	Versions V3-16 onwards should auto run from your CD drive.
	If it does not you can double click on
	install.html
	OR
	setup.exe

	If you are upgrading MCE from an earlier release please
	remember to uninstall the old version beforehand. Failure
	to do will result in a bad installation. The Uninstall 
	program (Add/Remove Programs) is found under Settings
	/Control Panel.
	
	Windows 95, 98 & Me
	For MCE and or MCELIB to function PCMCIA hardware must be
	installed on the PC and Card and Socket Services drivers
	enabled. 	

	Windows NT4, 2000 & XP
	MCE and MCELIB does not need Card and Socket Services
	software drivers to function. The only requirement is that
	the hardware is present and one of the supported types:

	Elan J-Series type PC-Card controller (ISA Interface)
	Elan P-Series type PC-Card controller (PCI Interface)
	Elan P111 type Cardbus controller (PCI Interface)
	or Intel 82365 compatible type controller (including Texas/Ricoh
	CardBus types).
	
	MORE HELP
	---------

	Please refer to the sections Installation / Troubleshooting 
	available in the help file MCEHELP.HLP. This file may be 
	found in the default directory c:\ElanPCCard\Memory Card
	Explorer. It can be read by double clicking it from the 
	Windows Explorer utility or called up directly from the MCE 
	application.
	For NT4/2000 installations also refer to the section NT4/2000 
	Notes.

	Additional Information 
	----------------------
	Installed to ElanPCCard sub-directories are :
	
	LICENSE.TXT  -Memory Card Explorer license agreement
	MCEHELP.HLP  -MCE product help guide

	MCELA.DOC    -Memory Card Explorer DLL license agreement
	MCEPG.DOC    -programmers user guide (WORD file)	
	MCELIB.H     -detailed API information for library functions
	LANG2DLL.TXT -language interfacing help for MCELIB 	
	MCEHDR.BAS   -Visual basic DLL library function definitions


	Installation Notes for MCELIB (program developers only)
	-------------------------------------------------------
95/98 & Me
----------
	Directories 
	-----------

	pccgo32.dll to	windows\system or same directory as application .exe
	pccardgo.vxd to	windows\system
	mcelib.dll in	windows\system or same directory as application .exe


NT4 & 2000
----------
	Directories 
	-----------

	pccgo32.dll to	winnt\system32 or same directory as application .exe
	pccgocls.sys to	winnt\system32\drivers
	mcelib.dll in	winnt\system32 or same directory as application .exe

	Registry
	--------

Make Registry Key:-
	\HKEY_LOCAL_MACHINE\System\CurrrentControlSet\Services\pccgocls
 & set the following values (Strings in quotes, all DWORDS for raw data):-	 
	NAME		VALUE
	Default
	DisplayName	"PcCGoCls"
	ErrorControl	0x00000000
	ImagePath	"\SystemRoot\System32\Drivers\PcCGoCls.sys"
	Start		0x00000002
	Type		0x00000001

The above key should be setup by the library developer as part of their install process.
W2000 & XP both require Unicode text files.

--------------------------------------------------------------------
REVISION NOTES/HISTORY:
--------------------------------------------------------------------
	Previous revision MCE V1-07 / MCELIB V1-08

	*************************************************
	MCE MCELIB ISSUE V2-00	Release date January 1999
	*************************************************

	ENHANCEMENTS

* Revision level of MCE/MCELIB unified.
* Card (block) addressing option added to MCE menu selection.
* Card (block) addressing function added to the MCELIB library.
* Install process for MCE product now one disk only.
* Card position control for Explore (Memory Card) menu option.
* Improved Flash Series 2+ card detection (MCELIB).
* Program reports a "no hardware 12V" warning message should
  the user attempt to write to a PC-Card requiring 12V on a 
  PC/Laptop that cannot provide it.

	CARD SUPPORT

* ID's added for SMT cards containing AMD C/D flash components.
* Installable full product components will not work with the
  demonstration product or the MCELIB DLL licenses purchased as
  the DLL ENGINE. Concise error messages are reported when an
  incompatibility is detected.
* Windows 98 supported.

	FIXES

* Certain Flash Series 2 cards were being wrongly identified as 
  Flash Series 2+, resulting in a failure to erase/write.
* Progress report error in DLL when filesize less than attribute
  size.

	NOTES

* Card addressing not available on demonstration version.



	*************************************************
	MCE MCELIB ISSUE V2-01	Release date March 1999
	*************************************************

	ENHANCEMENTS

* Customisation kit can now enable/disable toolbar buttons and
  the menu bar.

	CARD SUPPORT

* Support for new Intel flash components 28F160.
* Support for new AMD 'E' type 5V Flash components.

	FIXES

* MCE_SetAddresses() library function now passes an associated socket
  number to be evaluated. The requested start and end addresses can 
  then be evaluated for the card (if any) in that socket.  
* Intel Flash Series 2+ (FS2+) intermittent write fail fixed.
* FS2+ card detection failing (on laptops supplying 3.3V only to card).


	*************************************************
	MCE MCELIB ISSUE V3-00 Release date May 1999
	*************************************************

	ENHANCEMENTS

* NT4 Support added. Please also refer to the help file (mcehelp) 
  for more information on:

	Cards supported
	Interaction with other PCMCIA tools	
	PCMCIA Hardware support

  Note: Some AMD 'C' type cards fail to write under NT4.
	Check under later revisions for fix.

	*************************************************
	MCE MCELIB ISSUE V3-01 Release date June 1999
	*************************************************

	ENHANCEMENTS

* MCE screen update flicker on PC's with LCD displays reduced.

	FIXES

* All AMD 'C' type parts now work reliably on NT4 (pccgocls.sys update).
* Attribute memory bug corrected : auto-evaluated attribute memory set
  to 1/2 full size.
	
	*************************************************
	MCE MCELIB ISSUE V3-02 Release date August 1999
	*************************************************

	ENHANCEMENTS

* MCELIB now registers memory resource requirement with NT4. If this memory
  is not available then MCE will give an error message and terminate.
	
	FIXES

* Flash Series 1 cards : fail to erase (MCELIB.DLL update). Problem occurs
  on Windows 95/98 installations only.

* Strata Flash > 8MB were failing to program due to addressing s/ware fault.
  Problem corrected.

	*************************************************
	MCE MCELIB ISSUE V3-03 Release date December 1999
	*************************************************

	ENHANCEMENTS

* MCE/MCELIB now supports VCC override control. Cards can be powered to
  3.3 or 5.0V VCC provided the hardware can support this.
  Note : Elans P-Series hardware will require driver version 3-05 or greater. 
* MCELIB now supports CLF MLC Flash Cards (from Centennial).
* Basic library header mcehdr.bas provided for VB6 users.
* Dynamic link defines added to mcelib.h for C++ developers using
  the library. 
* Cards identified as being IO in Card CIS are not evaluated. The only exception
  to this are ATA cards. These may be evaluated provided an I/O address has been
  supplied for MCE/MCELIB to use.
* The library now supports a byte swapping feature. Odd and even bytes
  swapped over. The file mcelib.h function MCE_SetAddresses contains details.
* The library now supports a power hold feature which simply prohibits mce
  from changing the supplied Vcc/Vpp. See MCE_Customisations in mcelib.h.
* New function MCE_SetVccControl allows low voltage control for MCELIB users. See
  mcelib.h.
   
	FIXES

* Latest version corrects NT4 Status warnings Write Protect & Battery 
  Status which were being erroneously produced (fault in NT4 driver pccgo32.sys).
* Catalyst flash components now correctly detected as Series 1 flash cards.
* ATA timeout fix for Rotating ATA cards on some PC's. Symptom : Card would
  never size as insufficient time was allowed for it to become ready.


	*************************************************
	MCE MCELIB ISSUE V3-04 Release date February 2000
	*************************************************

	ENHANCEMENTS

* Manual Selection enhancements for FS2/FS2+ FLASH cards.
* Support for a new Strata Flash (MLC Flash) I.D. 
* CRC Checksumming utility added for DLL ENGINE disk (to verify supplied library
  object is error free).
* The MCE Customisation Kit now contains a Visual Basic 6 example front end. 	
* The MCE/MCEDEMO GUI's will now work with the protected or unprotected form of
  mcelib.dll. The demonstration library on the demo disk is now unprotected and so 
  can be used with the MCEDEMO program or a user written front end. Previously the 
  unprotected library was supplied separately in sub-directory "dll_eng".  For the
  full  unprotected  version of the library  the user still has to  purchase 
  "MCE DLL ENGINE" licenses.

	FIXES

* Flash Series 2 1M cards x8 bit were not sizing correctly
* MCE_OpWithFile() Library function : Passing a NULL pointer to the Abort Flag
  would cause a program crash.

	*************************************************
	MCE MCELIB ISSUE V3-05 Release date   March 2000
	*************************************************

NOTE : THIS IS A MCEDEMO RELEASE ONLY!

	ENHANCEMENTS

* MCEDEMO is now a Time limited version of the full product. The trial period
  provided is 30 days. 
* Library users can force card size tuple information to be ignored. Normally
  this value gets adopted if CARD TUPLE SIZE not equal to MCELIB EVALUATED SIZE.
  see MCE_Customisations().
* Additional Strata Flash ID's added.

	FIXES

* 3.3V Flash Series 2+ cards failing to write on hardware capable of providing
  the low Vcc voltage(3.3). Reason : Vpp was being set to 5V when it should match
  the 3.3V Vcc voltage level.
* Low Voltage control software introduced bug with logical/ physical slot number 
  allocation.  The effect was that 2nd slot would not detect cards properly. 
* Attribute : writing with a file smaller than the attribute range selected 
  would give a file read error.

	*************************************************
	MCE MCELIB ISSUE V3-06 Release date   March 2000
	*************************************************

	ENHANCEMENTS

* Library mods to better accommodate VB6 refer to mcelib.h and mcelib.hdr
* MCE CUSTOMISATION KIT : improved VB examples
* new PCCARDGO driver for NT4 - improvements for Ricoh 5C476
* new dialog added : setup / Other Features. Selections allow for IO and ATA
  adjustments and other features.
* Hyundai manufacturer added for C,D type flash parts + Hyundai 4m flash part id.
* Amd C,D type 3V Id's added for auto-detection

	FIXES

* DLL_ENGINE crc generating function required to be statically built to include
  all libraries.

	*************************************************
	MCE MCELIB ISSUE V3-07 Release date   April 2000
	*************************************************

	ENHANCEMENTS

* Windows 2000 release
* MCE initialisations file (mce.ini) is now provided on the disk in uncompressed
  form. This will allow the user to replace this file to customise the MCE install
  disk ready for a customers multi-platform installation.
* New selections under Setup/Other features:
  - Disable card erase and write warning messages
  - Disable auto verify after a card write operation 
* Fujitsu AMD Flash card added part ID 04,A4 (=AMD C/D part ID).    
* Card tuple Jedec ID shown in MCE Card Information dialog (only if CIS valid + 
  field present).
* Status line of MCE application now shows the card size in hexadecimal when a PCMCIA
  card is analysed as a result of an insertion or a slot change.

	FIXES

* Improvement of function MCE_IOCardTest in MCELIB -some IO cards were not being
  detected correctly as IO type.
* NT4 and 2000 with Texas CardBus 12xx/14xx contollers : ATA cards now supported
* Fujitsu part Id correction : ID (04,D5) put as flash S2 changed to AMD C/D type.
* Change to header file mcelib.h to accommodate Microsoft VC++ compiler V6.0 grumblings
 
	*************************************************
	MCE MCELIB ISSUE V3-08 Release date   August 2000
	*************************************************

	ENHANCEMENTS

* NT4/W2000 version - MCE memory window has no address constraint. Previously it 
  needed to be set within the linear address range of C0000-DFFFFH.

* New function MCE_Status() added for library users

* Manual Card selection. Flash Series 1 can select erase block size

	FIXES

* Manual Selection of MLC flash types providing incorrect card size range for part
  selection.  Bug present from version V3-05 to 3-07.

* Increased power up delay before card operations to prevent read/write errors. 
  Problem seen for particular card and PC hardware combinations.

* Card warning messages (Write Protect or Battery Low) erroneously reported by mcelib
  (under Windows 95/98/Mm).

* Problem seen with function MCE_IOCardTest (MCE 95/98/Mm users & developers using 
  this MCELIB function).  Certain card types with no attribute memory but card data 
  that looked like CIS information was getting miss-interpreted and ultimately causing
  a program lock-up.  MCE_IOCardTest function was first introduced for V3-03.

* File PCCARDGO.SYS causing problems on NT4/2000. Driver removed from installation as
  no longer required by the MCE/MCELIB products.

* PCCARDGO.VXD updated to version 1-09. This update allows some new laptops to function
  correctly when running Windows 98 or Millennium. <Fault symptom : card insertion never 
  detected by MCE and slot selection would get to 2nd slot and stay there instead of
  retuning to the first one.> Fault first seen on Panasonic CF-M1.


	*************************************************
	MCE MCELIB ISSUE V3-09 Release date  October 2000
	*************************************************

	ENHANCEMENTS

* Further Improvements to the MCE_IOCardTest() Function. (see V3-08 fixes) 

	*************************************************
	MCE MCELIB ISSUE V3-10 not released
	*************************************************

	*************************************************
	MCE MCELIB ISSUE V3-11 Release date November 2000
	*************************************************

	FIXES

* Ethernet PCMCIA cards were not being identified as IO type cards in MCELIB function
  MCE_IOCardTest(). This would cause problems with the Ethernet cards operation once 
  testing had finished for a valid memory card.
  Later tests may ID the card as being IO type but for the ethernet card setup to be 
  undisturbed the Id must occur in MCE_IOCardTest. For MCE users set the Menu option:
  Setup / Other Features / Do not interrogate I/O cards for Memory Card Signatures 
 
* Cardbus cards should not be dealt with by MCE or MCELIB. MCE/MCELIB should not
  detect a Cardbus card insertion. The message displayed by MCE will remain "No Card".
  MCELIB Library Users : The card insertion test MCE_Inserted() will return NO_CARD. 


	*************************************************
	MCE MCELIB ISSUE V3-12 Release date July 2001
	*************************************************

	ENHANCEMENTS : MCE
   
*  Overlay File feature added to the File menu options in MCE. This allows a second 
   selected file to overlay the currently selected file that is for use with card 
   operation functions read/write and compare.  This feature will allow users to
   position data for a card to any address where existing card functions are restricted
   to block boundaries governed by the PC-Card type.
   Typical steps : 
   1/. read card to 'card file'.  
   2/. overlay second file into cardfile specifying start and end offsets into card file.
   3/. write card file to PC-Card.    	

*  Extract Data from file feature added. This allows part of the data stored in the card
   file to be extracted to a second (destination file). The part written is determined 
   by Start and end addresses defined for the card file.  

*  Card Explore now has a file verify test incorporated to compare directly file and
   card values.

*  Card Explore will now also explore ATA card data as if it were 'Common Memory'.

*  File Explore has a data pattern search feature added.

*  Auto registration and test of mce driver registration for NT4/2000. MCE now gives a
   warning message when registration is incomplete and a system re-boot is required.
   MCE then closes and the operating system should be restarted.
   For library users MCE_CheckWindow() automatically registers / checks the registration
   of the drivers and warns if the system requires a re-boot before use.

	
	FIXES

*  MCE_Status call for library users not previously available for statically linked 
   projects.

*  During read ops a card ejection will cause a ST_OPFAIL error. (previously card
   insertion not monitored during an operation)

	*************************************************
	MCE MCELIB ISSUE V3-13 Release date October 2001
	*************************************************

	ENHANCEMENTS : MCE

*  The Card Explore option is now set to work with ATA, IO and Unknown card types.
   For ATA the common memory view looks at card data. Dissable the ATA options from
   the Menu Setup/Other Features and the true common memory data can also be viewed.
   IO and unknown card type are examined as if they are Memory Cards with common and 
   attribute memory banks. 	

*  Windows 95/98/Me versions can now work with a high memory window. This feature
   allows MCE Desktop support for PCI only motherboards using the Intel 810/815/820
   chipsets.
*  New function MCE_RestoreWindow() added for library users to de-allocate reservations
   made with MCE_CheckWindow(). Refer to MCELIB.h for more information.


	*************************************************
	MCE MCELIB ISSUE V3-14 Release date April 2002
	*************************************************

	ENHANCEMENTS : MCE

*  MCEDEMO has been not only restricted in lifetime but also the number of full operations
   available. Sorry, but Elan have decided that too many people may be satisfying their
   low one off/low volume PC card programming requirement by using MCEDEMO and never 
   purchasing MCE. 
   Note also that the demonstration version requires Administrator access rights for 
   WindowsNT4, 2000, XP.

	FIXES

*  MCELIB : ATA Card timeouts further adjusted for IBM Microdrives.

*  MCE : Memory leak on a card operation progress callback fixed. 
   The fault manifiests only on card operations > 440Mb. This memory loss clears at the  
   end of a card operation less than 440Mb and therefore only affects MCE users with 
   large ATA card types. 

*  On W2000/XP when logged in as a User the driver pccgocls will fail to load unless
   its startup property is modified from Load on "Demand" to "Automatic". This release
   addresses this issue in the install program.

*  Installation no longer adds line EmmExclude in windows file system.ini as it is not
   required.

	*************************************************
	MCE MCELIB ISSUE V3-15 Release date May 2002
	*************************************************

	FIXES

*  MCE : Versions of the full MCE product do not allow part card addressing. MCELIB/MCEDEMO
   variations work correctly. Problem introduced at release version 3-14. 


*  Instalation notes for MCELIB / registry changes in readme.txt modified

	*************************************************
	MCE MCELIB ISSUE V3-16 Release date August 2002
	*************************************************

	ENHANCEMENTS

* Install now using CD. 
* MCE Documentation provided in Adobe Acrobat PDF format (4).
* MCELIB Lib users: 3.3/5V card voltage requirement returned by the MCE_Status() Function. 

	FIXES

*  MCE : Versions of the full MCE product do not allow ATA initialisation. MCELIB/MCEDEMO
   variations work correctly. Problem introduced at release version 3-14. 

*  Users with problems using ATA cards on Cardbus type PCMCIA hardware may try the command
   line option 'A'. (Symptom: ATA sizes but fails card operations, fault seen with the
   following system: IBM Thinkpad A31p with Ricoh CB controller + W2000 O.S.). This 
   selection may also be passed to the library in the MCE_Customisations function.

--------------------------------------------------------------------
	End of readme.txt file
--------------------------------------------------------------------
