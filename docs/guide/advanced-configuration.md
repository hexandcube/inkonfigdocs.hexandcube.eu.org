# Advanced configuration

### TEMP and TMP enviromental variables
Allows to change the default location in which most programs place temporary files.

```batch
IF NOT EXIST "${VALUE}" ( mkdir ${VALUE} )
setx /m TEMP ${VALUE}
setx /m TMP ${VALUE}
setx TEMP ${VALUE}
setx TMP ${VALUE}
```

### Shutdown Event Tracker
Toggles the Shutdown Event Tracker that you can use to track the reason for system shutdowns.

![Screenshot of the Shutdown Event Tracker](/assets/images/docs/shutdownEventTracker.png)

=== "Enabled"
    ```batch
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT\Reliability" /v "ShutdownReasonOn" /t REG_DWORD /d "1" /f
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT\Reliability" /v "ShutdownReasonUI" /t REG_DWORD /d "1" /f
    ```
=== "Disabled"
    ```batch
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT\Reliability" /v "ShutdownReasonOn" /t REG_DWORD /d "0" /f
    REG add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT\Reliability" /v "ShutdownReasonUI" /t REG_DWORD /d "0" /f
    ```