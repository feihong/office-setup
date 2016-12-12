# Windows 10 Setup

## Ninite

Go to [Ninite](https://ninite.com), check the following applications, then run the downloader it gives you.

- Chrome
- Firefox
- 7-Zip
- VLC
- Python
- FileZilla
- PuTTY
- TeamViewer
- Revo
- PDFCreator
- KeePass 2

## Chocolatey

Open power shell in administrator mode and run:

```
Set-ExecutionPolicy RemoteSigned
iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")
Set-ExecutionPolicy Restricted
```

Install packages using Chocolatey:

```
choco install -y atom electron ccleaner
```

## Manual installation

Download and install:

- [SpiderOak ONE](https://spideroak.com/opendownload)
- [Adobe Acrobat Reader](https://get.adobe.com/reader/otherversions/) - Make sure to avoid the Reader DC option, which bundles crapware
- [Picasa](http://filehippo.com/download_picasa/) - Note that Picasa has been discontinued by Google and has some problems under Windows 10 (see Notes)

Install from ISO:

- Microsoft Office

## Manual configuration

- Sign in to Chrome
- Sign in to Firefox Sync

Some programs, e.g. VLC and SpiderOak ONE, will have icons or text that are too small because they are not DPI-aware. You'll have to [make some changes](dpi-aware.md) to inform the operating system that they are not DPI-aware. 

To enable Chinese support, open the Language control panel and click `Add a language`. Switch between input methods using Windows+Space.

Add sites in FileZilla.

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)
- [Reload the path in PowerShell](http://stackoverflow.com/questions/17794507/reload-the-path-in-powershell)
- [QHD 13" screen - Too small buttons](https://forum.videolan.org/viewtopic.php?t=121272)
- [How to Create ISO Files From Discs on Windows, Mac, and Linux](http://www.howtogeek.com/228886/how-to-create-iso-files-from-discs-on-windows-mac-and-linux/)

## Notes

To list all locally-installed packages: `choco list --local-only`

If you accidentally install crapware on your computer, use Revo to completely uninstall them from your computer.

In case you don't have the Product Key for Windows 10, you can get it by running ProduKey. You can install this program via `choco install produkey`.

Windows 10 has the built-in feature to mount ISO files. To create ISO files, consider using Mac OS X's DiskUtility app.

Under Windows 8.1 and 10, you cannot paste large-resolution images inside Picasa. The workaround is to paste a large image (such as a screenshot) into another program (such as Paint), and then open the image inside Picasa.
