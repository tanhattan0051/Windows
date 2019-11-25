## Windows Firewall

#### Open Ports
```
netsh advfirewall firewall add rule name="Open Port 80" dir=in action=allow protocol=TCP localport=80
netsh advfirewall firewall add rule name="Open Port 80" dir=out action=allow protocol=TCP localport=80
```

#### Allow Ping
```
netsh advfirewall firewall add rule name="ICMP Allow incoming V4 echo request" protocol=icmpv4:8,any dir=in action=allow
```


## Change port remote 
```
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp\" -Name PortNumber -Value 33389

```

```
New-NetFirewallRule -DisplayName "New RDP Port 33389" -Direction Inbound -LocalPort 33389 -Protocol TCP -Action allowNew-NetFirewallRule -DisplayName "New RDP Port 33389" -Direction Inbound -LocalPort 33389 -Protocol UDP -Action allow
```
