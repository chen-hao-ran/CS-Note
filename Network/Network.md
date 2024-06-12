# Some commands for network



## Solve the problem that user cannot connect to the internet on Win10 UMP applications when using proxy

### On powershell(administrator)

* cancel all UMP application
```
foreach ($n in (get-appxpackage).packagefamilyname) {checknetisolation loopbackexempt -a -n="$n"}
```
* recovery
```
checknetisolation LoopbackExempt -c
```



## View port occupancy

### On powershell

```
netstat -ano | findStr <portnum>
```





