# Personalization

### Computer Name

Changes the computer name. The name can be up to 15 characters long, and can't contain the following symbols: `~ ! @ # $ % ^ & * ( ) = + _ [ ] { } \ | ; : . ' " , < > / ? `. Changing the computer name is optional.

Example: `Hexandcube-PC`

```batch
WMIC computersystem where caption="%computername%" rename "USER_INPUT"
```

### Common File Extensions

Toggles the visibility of common file extensions in Windows Explorer.

![Common File Extensions - Example](/assets/images/common-file-extensions.png)

System default: `Hidden`

=== "Shown"

    ```batch
    REG add "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v HideFileExt /t REG_DWORD /d 0 /f
    ```
=== "Hidden"

    ```batch
    REG add "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v HideFileExt /t REG_DWORD /d 1 /f
    ```

### Hibernation
Toggles the Hibernation power option.

System default: `Disabled`

=== "Enabled"

    ```batch
    powercfg -H ON
    ```
=== "Disabled"

    ```batch
    powercfg -H OFF
    ```

### Seconds in the taskbar clock

!!! warning "Not supported on Windows 11"
    This feature doesn't work on Windows 11. [Visit the releated Feedback Hub post](https://aka.ms/AAd8div).

Toggles the visibility of seconds in the taskbar clock.

System default: `Disabled`

=== "Enabled"

    ```batch
    REG add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "ShowSecondsInSystemClock" /t REG_DWORD /d "1" /f
    ```
=== "Disabled"

    ```batch
    REG add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "ShowSecondsInSystemClock" /t REG_DWORD /d "0" /f
    ```

### Require CTRL + ALT + DEL to login
Toggles the requirement to press ++ctrl+alt+delete++ to log in to Windows.

System default: `Disabled`

=== "Enabled"

    ```batch
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon" /v "DisableCAD" /t REG_DWORD /d "0" /f
    ```
=== "Disabled"

    ```batch
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon" /v "DisableCAD" /t REG_DWORD /d "1" /f
    ```

### Verbose logon messages
Toggles the verbose startup, shutdown, logon, and logoff status messages.
Verbose status messages may be helpful when you're troubleshooting slow startup, shutdown, logon, or logoff behavior.

System default: `Disabled`

=== "Enabled"

    ```batch
    REG add "HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Policies\System" /v "VerboseStatus" /t REG_DWORD /d "1" /f
    ```
=== "Disabled"

    ```batch
    REG add "HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Policies\System" /v "VerboseStatus" /t REG_DWORD /d "0" /f
    ```

### Open Explorer to
Toggles the Open Explorer to option between Quick Access and This PC.

System default: `Quick Access`

=== "This PC"

    ```batch
    REG add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "LaunchTo" /t REG_DWORD /d "1" /f
    ```
=== "Quick Access"

    ```batch
    REG add "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v "LaunchTo" /t REG_DWORD /d "2" /f
    ```