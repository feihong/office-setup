# Use Mac OS X Disk Utility to create an ISO file

1. Start Disk Utility
1. Insert disc
1. Select `New > Disc Image from [Name of Disc]`
1. Once the process finishes, you will get a dmg file
1. To convert it to an ISO file, run:

   ```
   hdiutil convert /path/to/source.dmg -format UDTO -o /path/to/destination
   ```
1. The output file will have an extension of .cdr, but just change the extension to .iso and it should work just fine. You can even mount the .iso file on Windows 10.

## Source

[How to Create ISO Files From Discs on Windows, Mac, and Linux](http://www.howtogeek.com/228886/how-to-create-iso-files-from-discs-on-windows-mac-and-linux/)
