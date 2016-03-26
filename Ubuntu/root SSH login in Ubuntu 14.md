# Ubuntu 14.04 为 root 帐号开启 SSH 登录

## 1. 修改 root 密码
```
sudo passwd root
```

## 2. 以其他账户登录，通过 sudo nano 修改 /etc/ssh/sshd_config :
```
xxx@ubuntu14:~$ su - root
Password:
root@ubuntu14:~# vi /etc/ssh/sshd_config
```

## 3. 注释掉 #PermitRootLogin without-password，添加 PermitRootLogin yes
```
# Authentication:
LoginGraceTime 120
#PermitRootLogin without-password
PermitRootLogin yes
StrictModes yes
```

## 4. 重启 ssh  服务
```
root@ubuntu14:~# sudo service ssh restart
ssh stop/waiting
ssh start/running, process 1499
root@ubuntu14:~#
```
