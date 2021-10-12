# Script options

### Generated script file name
Changes the file name of the generated script. Default name is `InkonfigScript`.

### File Extension
Changes the file extension of the generated script. Default extension is `.bat`.

### Restart the computer after applying the configuration
When checked Inkonfig will restart the computer 5 seconds after exiting, with a reason `Operating System: Reconfiguration (Planned)`.

```batch
shutdown /r /t 5 /d P:2:4 /c "[Inkonfig] Restarting after configuring Windows"
```