# Windows 10 Setup

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

Download and install

- [SpiderOak ONE](https://spideroak.com/opendownload)

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)

## Notes

To list all locally-installed packages: `choco list --local-only`
