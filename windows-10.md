# Windows 10 Setup

Open power shell in administrator mode and run:

```
Set-ExecutionPolicy RemoteSigned
iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")
```

Install packages using Chocolatey:

```
choco install -y firefox googlechrome filezilla 7zip putty adobereader
```

## Sources

- [Installing Chocolatey](https://chocolatey.org/install)
