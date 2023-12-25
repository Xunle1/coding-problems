# Use Chrony To Synchronize Time

Install chrony

```shell
sudo apt install chrony
```

Edit `/etc/chrony/chrony.conf`

```
server ntp.ntsc.ac.cn prefer
server ntp1.aliyun.com
```

Restart chrony service

```
sudo systemctl restart chrony.service
```

Wait a few minutes. Check the status.

```shell
chronyc sources -v

#   .-- Source mode  '^' = server, '=' = peer, '#' = local clock.
#  / .- Source state '*' = current best, '+' = combined, '-' = not combined,
# | /             'x' = may be in error, '~' = too variable, '?' = unusable.
# ||                                                 .- xxxx [ yyyy ] +/- zzzz
# ||      Reachability register (octal) -.           |  xxxx = adjusted offset,
# ||      Log2(Polling interval) --.      |          |  yyyy = measured offset,
# ||                                \     |          |  zzzz = estimated error.
# ||                                 |    |           \
# MS Name/IP address         Stratum Poll Reach LastRx Last sample               
# ===============================================================================
# ^? 114.118.7.161                 1   6    12   184    +34ms[  +34ms] +/-   55ms
# ^* 120.25.115.20                 2   6   253    54    -72us[ -323us] +/-   16ms
```

Change the timezone

```shell
cp /etc/localtime /etc/localtime.bak
ln -svf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```

Check the date

```shell
date

# Mon Dec 25 17:29:04 CST 2023
```
