# Windows 10 Setup

## Ninite

Go to [Ninite](https://ninite.com), check the following applications, then run the downloader it gives you.

- Chrome
- Firefox
- Skype
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
```

Install packages using Chocolatey:

```
choco install -y atom electron
```

## Manual installation

Download and install:

- [SpiderOak ONE](https://spideroak.com/opendownload)
- [Adobe Acrobat Reader](https://get.adobe.com/reader/otherversions/) - Make sure to avoid the Reader DC option, which bundles crapware

## Manual configuration

- Sign in to Chrome
- Sign in to Firefox Sync

Some programs, e.g. VLC and SpiderOak ONE, will have icons or text that are too small because they are not DPI aware. You'll have to [make some changes](dpi-aware.md) to inform the operating system that they are not DPI-aware. 

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)
- [Reload the path in PowerShell](http://stackoverflow.com/questions/17794507/reload-the-path-in-powershell)
- [QHD 13" screen - Too small buttons](https://forum.videolan.org/viewtopic.php?t=121272)

## Notes

To list all locally-installed packages: `choco list --local-only`
