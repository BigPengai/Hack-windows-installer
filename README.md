# Hack Windows Installer

A Windows installer for the [Hack](https://github.com/chrissimpkins/Hack) typeface.

While it might seem like overkill to use a Windows installer for fonts, there is good reason for this on the Windows platform. A number of things can go wrong when one tries to install or update frequently updated fonts manually (see [issue #152](https://github.com/chrissimpkins/Hack/issues/152) and [issue #129](https://github.com/chrissimpkins/Hack/issues/129) in the [Hack repository](https://github.com/chrissimpkins/Hack/)). 

This installer addresses most of the [commonly obeserved issues](https://github.com/source-foundry/Hack-windows-installer/blob/master/FontInstallationIssues.md).


## Usage

- Download `HackWindowsInstaller.exe` from [Releases](https://github.com/source-foundry/Hack-windows-installer/releases/latest)
- Double click `HackWindowsInstaller.exe`
- If you see a *Windows protected your PC* message, click on `More info` and select `Run anyway`. This *Windows SmartScreen warning* can be safely ignored, the installer is virus and addware free (see VirusTotal report for each release) 
- Follow the installation instructions

## Installer Source

You may review the comment annotated installer source in [HackWindowsInstaller.iss](https://github.com/source-foundry/Hack-windows-installer/blob/master/src/HackWindowsInstaller.iss).

To build this setup yourself, download the most recent ANSI (not Unicode) version of [Inno Setup](http://www.jrsoftware.org/isdl.php). Install it and activate the option to install the [Inno Setup Preprocessor](http://www.jrsoftware.org/ispphelp/). Double-click `HackWindowsInstall.iss` (folder `src`), which will load it in Inno Setup and select *Build* - *Compile*.

We release the compiled installer with its SHA256 hash digest and [VirusTotal](https://virustotal.com/en/) malware scan report link in [Releases](https://github.com/source-foundry/Hack-windows-installer/releases/latest).


## Silent Installation

To install silently, use the following command:

 ``start /wait HackWindowsInstaller.exe /VERYSILENT /SUPPRESSMSGBOXES /NORESTART /CLOSEAPPLICATIONS /NORESTARTAPPLICATIONS``

To remove it silently:

 ``C:\Program Files\Hack Windows Installer\unins000.exe /VERYSILENT /SUPPRESSMSGBOXES /NORESTART``


## Troubleshooting

The installer creates a log file on the path `C:\Users\ (Username) \AppData\Local\Temp\Setup Log (Year-Month-Day) #XXX.txt` with full information, as well as `C:\Program Files\Hack Windows Installer\Log-FontData.txt`. The later only contains a subset of the first. 

If you are using EMET: If the "Only trusted fonts" option is activated, you need to declare Hack as trusted or it will not be usable.


## Contributions

Any constructive contribution is very welcome! 

In order to fix a bug you have encountered, we require the log file. To view this log file, do the following:

- Open the folder `C:\Program Files\Hack Windows Installer`
- Locate the file called `Log-FontData.txt`
- Open a new [issue](https://github.com/source-foundry/Hack-windows-installer/issues/new)
- Paste the entire text of the log file  


## License
Copyright © 2016 [Michael Hex](http://www.texhex.info/) / Source Foundry. Licensed under the **MIT License**. For details, please see [LICENSE.txt](https://github.com/source-foundry/Hack-windows-installer/blob/master/LICENSE.txt).
