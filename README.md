# Oracle Cent OS SSR 

## Replace Kernel && Install BBR Plus(Not Stable)
```
sudo su

cd /etc/
wget https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/bbrplus/centos/7/kernel-4.14.129-bbrplus.rpm
rpm -ivh kernel-4.14.129-bbrplus.rpm --force
rpm -qa | grep kernel
grub2-mkconfig -o /boot/grub2/grub.cfg
grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg
cat /boot/grub2/grub.cfg |grep menuentry
grub2-set-default 'CentOS Linux (4.14.129-bbrplus) 7 (Core)'
reboot

sudo su
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"
chmod +x tcp.sh
./tcp.sh
```

## Update Original Kernel && Install BBR Plus
```
sudo su

cd /etc/
rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-3.el7.elrepo.noarch.rpm
cat /boot/grub2/grub.cfg |grep menuentry
grub2-set-default 'CentOS Linux (5.3.11-1.el7.elrepo.x86_64) 7 (Core)'
vim /etc/sysctl.conf
```
net.core.default_qdisc = fq
net.ipv4.tcp_congestion_control = bbr
```

reboot
```

## Install SSR
```
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
chmod +x shadowsocksR.sh
```
