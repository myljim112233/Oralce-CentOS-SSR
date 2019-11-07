# Oracle Cent OS SSR 
## Replace Kernel && Install BBR Plus
```
sudo su

cd /etc/
wget https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/bbrplus/centos/7/kernel-4.14.129-bbrplus.rpm
rpm -ivh kernel-4.14.129-bbrplus.rpm –force
rpm -qa | grep kernel
grub2-mkconfig -o /boot/grub2/grub.cfg
grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg
cat /boot/grub2/grub.cfg |grep menuentry
grub2-set-default ‘CentOS Linux (4.14.129-bbrplus) 7 (Core)’
reboot

sudo su
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"
chmod +x tcp.sh
./tcp.sh
```
## Install SSR
```
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```
