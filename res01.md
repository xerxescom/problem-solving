1、Ubuntu20.04安装VMware Tools

```
sudo apt install open-vm-tools-desktop -y
sudo reboot
```



2、Docker自动安装脚本

```
sudo apt update
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
```



3、解决E: 无法获得锁 /var/lib/apt/lists/lock。锁正由进程 1548（packagekitd）持有

```
ps aux | grep packagekitd

sudo kill 1548

sudo rm /var/lib/apt/lists/lock
```

4、解决permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json?all=1": dial unix /var/run/docker.sock: connect: permission denied

```
sudo groupadd docker
sudo usermod -aG docker $USER
sudo chown 777 /var/run/docker.sock
sudo service docker restart

或者（在设置root密码的基础上）
su root
sudo groupadd docker               #添加用户组
sudo gpasswd -a username docker    #将当前用户添加至用户组
newgrp docker                      #更新用户组


```
