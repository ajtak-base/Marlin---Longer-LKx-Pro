# Marlin 2.1 Printer Firmware For Longer LK4/LK5 Pro and Alfawise U30 Pro.

**IMPORTANT!!** This firmware will not work on touch screens other than model DW. In the About, the screen firmware version may have letters following it like "0.3.1-DW". This firmware will only work if your screen has the letters DW or no letters following the version number.

**Do not try to update if your touch screen model is "T5L", "DWTJ" or "DWTJB".** 

Here are brief installation instructions:
1. Download the appropriate Marlin hex file for your system configuration as well as the DWIN_SET from the release page.
2. Download and install the Longer slicer from Longer's official web site.
3. Connect a USB cable from your computer to the printer.
4. Open the Longer slicer and select Machine / Machine Settings.
5. Open the Serial Port selection and select the serial port for the printer. If there is no port available under the selection, then you must troubleshoot your USB connection before proceeding.
6. If a port was selected, set the Baud Rate to Auto. Note that the baud rate may change after installation. You will need to account for this in any control software you are using. The new baud rate is 115200.
7. Select the OK button to save the settings.
8. On Longer Slicer, select Machine / Install Custom Firmware.
9. Locate the new firmware .hex file. The firmware should update. If it does not update, do not proceed.
10. Now use a Micro SD card between 4 GB and 16 GB and format it for FAT32 with a cluster size (allocation size) of 4096 bytes. Otherwise, the display will not recognize the SD card. 
11. Extract the DWIN_SET folder from the .zip file and copy it to the formatted SD card.
12. Open the frame around the display screen and place the SD card into the SD slot for the screen.
13. Disconnect the USB cable from the computer before proceeding.
14. Power on the printer and the screen software should update. It takes about 1 minute. When complete, the first displayed line will say "SD Card Process... END !".
15. Remove the SD card and cycle the power on the printer. The printer should come up.

**Notes:** 

If you are running Windows Home Edition, it will not have a Utilization of 4096 KB availabile. In this case open a Command Prompt on the PC and enter the following command. FORMAT D: /FS:FAT32 /Q /A:4096 where D: is the drive letter assigned to your SD card. This format must be used to update the screen software.

The new screens will not work with the old software. You MUST either have the new firmware and new screens or the old firmware and old screens. Load the Firmware first. Then the screen software. Steps 4 thru 9 can be done using the Prusa slicer, Cura, Octoprint, Repetier Server, Arduino, Avrdude, or any other firmware updater for Arduino. Follow instructions. In step 10, the SD card MUST be formatted as FAT32 with a Utilization of 4096 KB. The screen will not update unless this format is used. Warning! Loading this new firmware will reset your print counts.

The default probe offset is set to an X offset of -32. This is correct if you have a single blower. If your unit has a dual blower, go to the Gcode entry screen and enter the commands M851 X-50 to set the X probe offset and M500 to save the settings.

If you have already loaded the display software and you are only updating the firmware, you can skip lines 10 thru 15.

<h1 align="center">Marlin 3D Printer Firmware</h1>

<p align="center">
    <a href="/LICENSE"><img alt="GPL-V3.0 License" src="https://img.shields.io/github/license/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/releases"><img alt="Last Release Date" src="https://img.shields.io/github/release-date/MarlinFirmware/Marlin"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/actions"><img alt="CI Status" src="https://github.com/MarlinFirmware/Marlin/actions/workflows/test-builds.yml/badge.svg"></a>
    <a href="https://github.com/sponsors/thinkyhead"><img alt="GitHub Sponsors" src="https://img.shields.io/github/sponsors/thinkyhead?color=db61a2"></a>
    <br />
    <a href="https://twitter.com/MarlinFirmware"><img alt="Follow MarlinFirmware on Twitter" src="https://img.shields.io/twitter/follow/MarlinFirmware?style=social&logo=twitter"></a>
</p>

Additional documentation can be found at the [Marlin Home Page](https://marlinfw.org/).
Please test this firmware and let us know if it misbehaves in any way. Volunteers are standing by!

## Modifications

This is based on the work from DaGr70 https://github.com/DaGr70/Marlin_Longer_LK4_pro and Desuuuu https://github.com/Desuuuu/Marlin.

I wanted more features and a more consistent look on the touchscreen. I made these modifications but more features will be added over time.
- Added advanced settings to allow changing Steps/mm, Acceleration and more from the touchscreen.
- Reworked some screens layout and navigation.
- Enabled the M600 command by default.
- Enabled power loss recovery by default.
- Works with non-BLtouch printers

You can see some screenshots here https://github.com/Guizz27/DWIN_LK4Pro/tree/main/Screenshots.

Integrated all changes from https://github.com/Desuuuu/Marlin and https://github.com/MarlinFirmware/Marlin to stay up to date with Marlin and the Reloaded screens updates.

Releases will contain the touchscreen firmware that matches. If you want the source of the screen firmware you can find it here https://github.com/Guizz27/DWIN_LK4Pro.

## Building Marlin 2.1

To build Marlin 2.1 you'll need [Arduino IDE 1.8.8 or newer](https://www.arduino.cc/en/main/software) or [PlatformIO](http://docs.platformio.org/en/latest/ide.html#platformio-ide).

## Building and installing Marlin 2.1 for LKx Pro
Baddflash wrote detailed instructions to build and install the printer firmware as well as the screen firmware which you also have to update. Instructions are for an older version, so you will need to adapt to this new 2.1 version.
Please follow his instructions here: https://github.com/Baddflash/LK4-Pro-Firmware-Tutorial

### Supported Platforms
  
  Platform|MCU|Example Boards
  --------|---|-------
  [Arduino AVR](https://www.arduino.cc/)|ATmega|RAMPS, Melzi, RAMBo

  Although this is based on the official Marlin software. The configuration files are specific to Longer/Alfawise "Pro" printers.
  It may or may not build for other platforms.

## Marlin Support

The Issue Queue is reserved for Bug Reports and Feature Requests. To get help with configuration and troubleshooting, please use the following resources:

- [Marlin Documentation](https://marlinfw.org) - Official Marlin documentation
- [Marlin Discord](https://discord.gg/n5NJ59y) - Discuss issues with Marlin users and developers
- Facebook Group ["Marlin Firmware"](https://www.facebook.com/groups/1049718498464482/)
- RepRap.org [Marlin Forum](https://forums.reprap.org/list.php?415)
- Facebook Group ["Marlin Firmware for 3D Printers"](https://www.facebook.com/groups/3Dtechtalk/)
- [Marlin Configuration](https://www.youtube.com/results?search_query=marlin+configuration) on YouTube

## Contributors

Marlin is constantly improving thanks to a huge number of contributors from all over the world bringing their specialties and talents. Huge thanks are due to [all the contributors](https://github.com/MarlinFirmware/Marlin/graphs/contributors) who regularly patch up bugs, help direct traffic, and basically keep Marlin from falling apart. Marlin's continued existence would not be possible without them.

## Administration

Regular users can open and close their own issues, but only the administrators can do project-related things like add labels, merge changes, set milestones, and kick trolls. The current Marlin admin team consists of:

 - Scott Lahteine [[@thinkyhead](https://github.com/thinkyhead)] - USA - Project Maintainer &nbsp; [💸 Donate](https://www.thinkyhead.com/donate-to-marlin)
 - Roxanne Neufeld [[@Roxy-3D](https://github.com/Roxy-3D)] - USA
 - Keith Bennett [[@thisiskeithb](https://github.com/thisiskeithb)] - USA &nbsp; [💸 Donate](https://github.com/sponsors/thisiskeithb)
 - Peter Ellens [[@ellensp](https://github.com/ellensp)] - New Zealand
 - Victor Oliveira [[@rhapsodyv](https://github.com/rhapsodyv)] - Brazil
 - Chris Pepper [[@p3p](https://github.com/p3p)] - UK
 - Jason Smith [[@sjasonsmith](https://github.com/sjasonsmith)] - USA
 - Luu Lac [[@shitcreek](https://github.com/shitcreek)] - USA
 - Bob Kuhn [[@Bob-the-Kuhn](https://github.com/Bob-the-Kuhn)] - USA
 - Erik van der Zalm [[@ErikZalm](https://github.com/ErikZalm)] - Netherlands &nbsp; [💸 Donate](https://flattr.com/submit/auto?user_id=ErikZalm&url=https://github.com/MarlinFirmware/Marlin&title=Marlin&language=&tags=github&category=software)

## License

Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.

While we can't prevent the use of this code in products (3D printers, CNC, etc.) that are closed source or crippled by a patent, we would prefer that you choose another firmware or, better yet, make your own.

## Disclaimer
Please note that you use this software at your own risks. I am not responsible for any damage it may cause.
