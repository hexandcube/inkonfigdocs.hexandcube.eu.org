# Software

### Install Software using Chocolatey
When this option is checked, Inkonfig  will install the [Chocolatey Package Manager](https://chocolatey.org) (Unless the `I already have the Chocolatey Package Manager Installed` option is checked), and use it to install specified packages.

!!! Tip
    The list of available Chocolatey packages is available on [https://community.chocolatey.org/packages](https://community.chocolatey.org/packages).

!!! Warning "Community Package Repository Notification"
    Your use of the packages on this site means you understand they are not supported or guaranteed in any way. Due to the nature of a public repository and unreliability due to distribution rights, these packages should not be used as is for organizational purposes either. [Learn more](https://docs.chocolatey.org/en-us/community-repository/community-packages-disclaimer).

**Installing Chocolatey**

```batch
@"%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\\chocolatey\\bin"
```

**Installing packages using Chocolatey**

```batch
choco install ${VALUE} --y --acceptlicense --ignoredetectedreboot
```

## Bloatware and Ads

### Ads and unwanted apps
Toggles registry keys responsible for ads, automatic installation of sponsored apps, suggestions in the Start Menu and lockscreen, etc.

=== "Enabled"
    ```batch
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "ShowSyncProviderNotifications" /t REG_DWORD /d "1" /f
    REG add "HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SilentInstalledAppsEnabled" /t REG_DWORD /d "1" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SystemPaneSuggestionsEnabled" /t REG_DWORD /d "1" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SoftLandingEnabled" /t REG_DWORD /d "1" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "RotatingLockScreenEnabled" /t REG_DWORD /d "1" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "RotatingLockScreenOverlayEnabled" /t REG_DWORD /d "1" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SubscribedContent-310093Enabled" /t REG_DWORD /d "1" /f
    ```
=== "Disabled"
    ```batch
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "ShowSyncProviderNotifications" /t REG_DWORD /d "0" /f
    REG add "HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SilentInstalledAppsEnabled" /t REG_DWORD /d "0" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SystemPaneSuggestionsEnabled" /t REG_DWORD /d "0" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SoftLandingEnabled" /t REG_DWORD /d "0" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "RotatingLockScreenEnabled" /t REG_DWORD /d "0" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "RotatingLockScreenOverlayEnabled" /t REG_DWORD /d "0" /f
    REG add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" /v "SubscribedContent-310093Enabled" /t REG_DWORD /d "0" /f
    ```

## Windows Subsystem for Linux (WSL)
When checked, Inkonfig will install the Windows Subsystem for Linux. Inkonfig allows users, to specify a Linux distribution to install (Ubuntu by default). 

!!! Info "Note"
    The method of installing WSL used by Inkonfig, will only work on Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11.
    If you're running an older build, or prefer to install WSL manually, see [Manual installation steps for older versions of WSL](https://docs.microsoft.com/en-us/windows/wsl/install-manual).

```batch
wsl --install -d ${VALUE}
```