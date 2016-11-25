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

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)
- [Reload the path in PowerShell](http://stackoverflow.com/questions/17794507/reload-the-path-in-powershell)

## Notes

To list all locally-installed packages: `choco list --local-only`
