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

[Link](https://www.nextofwindows.com/allow-server-running-inside-wsl-to-be-accessible-outside-windows-10-host)

### hyper-v port forwarding

Create

```sh
netsh interface portproxy add v4tov4 listenport=3000 listenaddress=0.0.0.0 connectport=3000 connectaddress=172.30.208.115
```

Delete 

```sh
netsh interface portproxy delete v4tov4 listenport=3000 listenaddress=0.0.0.0
```

List

```sh
netsh interface portproxy show v4tov4
```
