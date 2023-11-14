# Set Proxy In Powershell

- Using netsh.

```powershell
# show proxy
netsh winhttp show proxy
# set proxy
netsh winhttp set proxy 127.0.0.1:7890
# reset proxy
netsh winhttp reset proxy
```

- env

```powershell
$env:HTTP_PROXY="http://127.0.0.1:7890"
$env:HTTPS_PROXY="http://127.0.0.1:7890"
```