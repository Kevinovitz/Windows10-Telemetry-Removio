# Windows10-Telemetry-Removio
Kill telemetry processes before they begin without removing a bunch of stuff. 

Using Image File Execution Options it is possible to terminate the telemetry process before it starts. 

Add the following registry entries to the registry. 

## Privacy / Telemetry

'''cmd
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\wsqmcons.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\CompatTelRunner.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\devicecensus.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\gamebarpresencewriter.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\wwahost.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
'''

## Microsoft Update

'''cmd
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\MusNotification.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\MusNotificationUx.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\MusNotifyIcon.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
'''

## Microsoft Edge

'''cmd
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\elevation_service.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\edgeupdate.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Option\MicrosoftEdgeUpdate.exe" /v Debugger /t REG_SZ /d "%windir%\System32\taskkill.exe" /f
'''

## References

- https://www.reddit.com/r/Windows10/comments/y2zteh/there_is_a_real_way_to_desactivate_windows/
- https://github.com/adolfintel/Windows10-Privacy/issues/4
