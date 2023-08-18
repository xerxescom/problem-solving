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

