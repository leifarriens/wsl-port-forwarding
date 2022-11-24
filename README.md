# wsl-port-forwarding

## Create firewall rules

[Link](https://www.nextofwindows.com/allow-server-running-inside-wsl-to-be-accessible-outside-windows-10-host)

## hyper-v port forwarding

Create

```sh
netsh interface portproxy add v4tov4 listenport=3000 listenaddress=0.0.0.0 connectport=3000 connectaddress=172.30.208.115
```

Delete 

```sh
netsh interface portproxy delete v4tov4 listenport=3000 listenaddress=0.0.0.0
```
