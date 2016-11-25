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
- PDFCreator

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

## Manual configuration

- Sign in to Chrome
- Sign in to Firefox Sync

Some programs, e.g. VLC and SpiderOak ONE, will have icons or text that are too small because they are not DPI aware. You'll have to create a .manifest file for each such program that contains the following contents:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0" xmlns:asmv3="urn:schemas-microsoft-com:asm.v3">

<dependency>
  <dependentAssembly>
    <assemblyIdentity
      type="win32"
      name="Microsoft.Windows.Common-Controls"
      version="6.0.0.0" processorArchitecture="*"
      publicKeyToken="6595b64144ccf1df"
      language="*">
    </assemblyIdentity>
  </dependentAssembly>
</dependency>

<dependency>
  <dependentAssembly>
    <assemblyIdentity
      type="win32"
      name="Microsoft.VC90.CRT"
      version="9.0.21022.8"
      processorArchitecture="amd64"
      publicKeyToken="1fc8b3b9a1e18e3b">
    </assemblyIdentity>
  </dependentAssembly>
</dependency>

<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="asInvoker"
        uiAccess="false"/>
    </requestedPrivileges>
  </security>
</trustInfo>

<asmv3:application>
  <asmv3:windowsSettings xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">
    <ms_windowsSettings:dpiAware xmlns:ms_windowsSettings="http://schemas.microsoft.com/SMI/2005/WindowsSettings">false</ms_windowsSettings:dpiAware>
  </asmv3:windowsSettings>
</asmv3:application>

</assembly>
```

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)
- [Reload the path in PowerShell](http://stackoverflow.com/questions/17794507/reload-the-path-in-powershell)
- [QHD 13" screen - Too small buttons](https://forum.videolan.org/viewtopic.php?t=121272)

## Notes

To list all locally-installed packages: `choco list --local-only`
