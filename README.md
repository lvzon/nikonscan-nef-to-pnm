# nikonscan-nef-to-tiff
A simple command-line tool to convert a Nikon Scan NEF file to TIFF

The [Nikon Scan](https://www.nikonimgsupport.com/eu/BV_article?articleNo=000044682) software which was shipped with the excellent Nikon Coolscan slide and negative scanners has the option to write scanned images to a "raw" file with the extension NEF. Unfortunately these files are not compatible with the raw NEF images that are produced by Nikon digital cameras, which is impractical and confusing. The NEF files produced by NikonScan are actually TIFF-files without compression and with an extra preview image embedded into the file. This simple command line tool takes a NikonScan NEF as input, strips off the extra information and writes a TIFF file to the standard output.

Usage:
'''
nikonscan-net2tiff input.nef >output.tif
'''

To compile this program, you will need a C-compiler such as GCC.

To install GCC in Debian or Ubuntu Linux, run:
'''
sudo apt install build-essential
'''

In order to install GCC on Mac, first install [Homebrew](https://brew.sh) and then type:
'''
brew install gcc
'''

For Windows, you'll need to install [MinGW](https://sourceforge.net/projects/mingw/).

To compile the program with GCC:

'''
gcc -o nikonscan-nef2tiff nikonscan-nef2tiff.c
'''

Of course you can also use Clang or another C-compiler.
