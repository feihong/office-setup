# Windows 10: Dealing with Programs That Are Not DPI Aware

## Use external manifest file

### Change registry

- Press Windows Button + R, type “regedit”, and then click OK.
- Navigate to the following registry subkey:
- HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > SideBySide
- Right-click, select NEW > DWORD (32 bit) Value
- Type PreferExternalManifest, and then press ENTER.
- Right-click PreferExternalManifest, and then click Modify.
- Enter Value Data 1 and select Decimal.
- Click OK. Exit Registry Editor.

### Create external manifest file

Navigate to the directory where the program's .exe file resides, and create a corresponding manifest file. For example, if
it's VLC you'd go to `C:\Program Files\VideoLAN\VLC` and create a file named `vlc.exe.manifest`. That file should have the following
content:

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

## Change the properties of the .EXE file

Instructions I got from a support email:

> First, completely shut down SpiderOak (right-click the icon in your system tray and click Quit, or end the SpiderOak processes in Task Manager). Then, open Windows' file explorer, navigate to C:\Program Files\SpiderOakONE\SpiderOakONE.exe and right-click the executable. There, click Properties, and then Compatibility. There should be an option there for "Disable display scaling on high DPI settings". Select that, click Apply, and then relaunch SpiderOak.

## Sources

- [QHD 13" screen - Too small buttons](https://forum.videolan.org/viewtopic.php?t=121272)
- [Adobe App Scaling on High DPI Displays (FIX)](http://www.danantonielli.com/adobe-app-scaling-on-high-dpi-displays-fix/)
