# wsl

## wsl-backup

### Create backup

```ps
wsl --export Ubuntu "C:\wsl_bk\ubuntu.tar"
```

### Restore form backup

```ps
wsl --unregister <distribution>
```

```ps
wsl --import Ubuntu "C:\wsl_bk\ubuntu.tar"
```

## wsl-port-forwarding

### Create firewall rules

```powershell
New-NetFirewallRule -DisplayName "Allow Port 3000" -Direction Inbound -Protocol TCP -LocalPort 3000 -Action Allow
```
or via Gui: [Link](https://www.nextofwindows.com/allow-server-running-inside-wsl-to-be-accessible-outside-windows-10-host)

### hyper-v port forwarding

Create

```sh
netsh interface portproxy add v4tov4 listenport=3000 listenaddress=0.0.0.0 connectport=3000 connectaddress=<wsl_ip>
```

Get the wsl ip:

```powershell
wsl hostname -I
```

Delete 

```sh
netsh interface portproxy delete v4tov4 listenport=3000 listenaddress=0.0.0.0
```

List

```sh
netsh interface portproxy show v4tov4
```
