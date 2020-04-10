# CMD
```
powercfg /x -hibernate-timeout-ac 0
powercfg /x -hibernate-timeout-dc 0
powercfg /x -disk-timeout-ac 0
powercfg /x -disk-timeout-dc 0
powercfg /x -monitor-timeout-ac 0
powercfg /x -monitor-timeout-dc 0
Powercfg /x -standby-timeout-ac 0
powercfg /x -standby-timeout-dc 0
```

# Registry
```
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FlyoutMenuSettings]
"ShowHibernateOption"=dword:00000000
"ShowSleepOption"=dword:00000000
```
