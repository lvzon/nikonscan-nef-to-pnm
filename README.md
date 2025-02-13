# nikonscan-nef-to-tiff
A simple command-line tool to convert a Nikon Scan NEF file to TIFF

The [Nikon Scan](https://www.nikonimgsupport.com/eu/BV_article?articleNo=000044682) software which was shipped with the Nikon Coolscan slide and negative scanners has the option to write scanned images to a "raw" file with the extension NEF. Unfortunately these files are not compatible with the raw NEF images that are produced by Nikon digital cameras, which is impractical and confusing. The NEF files produced by NikonScan are actually TIFF-files without compression and with an extra preview image embedded into the file. This simple command line tool takes a NikonScan NEF as input, strips off the extra information and writes a TIFF file to the standard output.

Usage:
```
nikonscan-net2tiff input.nef >output.tif
```

To compile this program, you will need a C-compiler such as GCC.     
To install GCC in Debian or Ubuntu Linux, run: `sudo apt install build-essential`     
In order to install GCC on Mac, first install [Homebrew](https://brew.sh) and then type: `brew install gcc`     
For Windows, you'll need to install [MinGW](https://sourceforge.net/projects/mingw/).

To compile the program with GCC:
```
gcc -o nikonscan-nef2tiff nikonscan-nef2tiff.c
```
Of course you can also use Clang or another C-compiler.

The Nikon Coolscan is still an excellent scanner, but unfortunately its drivers do not work well on modern operating systems. 
My advice to users who still have an old Nikon Coolscan and want to use it on a modern computer would be to install [VirtualBox](https://www.virtualbox.org) and its [Extension Pack](https://www.virtualbox.org/wiki/Downloads). Then find and install a copy of [Windows XP](https://archive.org/details/WinXPProSP3x86) on a virtual harddisk in VirtualBox, and install [Nikon Scan](https://www.nikonimgsupport.com/eu/BV_article?articleNo=000044682) on the virtual machine. If you [assign](https://www.virtualbox.org/manual/topics/BasicConcepts.html#usb-support) the Coolscan USB device to VirtualBox, the scanner will work fine (if a little more slowly than on native hardware). It is also possible to use the [Windows Visa-version](https://www.nikonimgsupport.com/eu/BV_article?articleNo=000050788&lang=en_GB) of NikonScan on Windows 10 or 11 with a [modified driver](https://www.sevenforums.com/drivers/44994-getting-your-nikon-coolscan-work-w7-x64.html), but unfortunately this does cause issues with batch scanning on some setups.

This program is written by Levien van Zon and is free software.
It is licensed under the GNU GPL version 3 or later.
That means you are free to use this program for any purpose;
free to study and modify this program to suit your needs;
and free to share this program or your modifications with anyone.
If you share this program or your modifications
you must grant the recipients the same freedoms.
To be more specific: you must share the source code under the same license.
For details see https://www.gnu.org/licenses/gpl-3.0.html
