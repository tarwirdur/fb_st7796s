# Драйвер для экрана MKS TS35 V2.0

DTS для orange pi zero2

Драйвер для экрана на контроллере st7796. [Описание установки и настройки](https://sergey1560.github.io/fb4s_howto/mks_ts35/)

```
Armbian 24.2.1:
https://drive.google.com/drive/folders/1ADDWz24VINz5_vMJfSuIpZx0Qpwhe2uL?usp=sharing


apt update
apt install -y linux-headers-current-sunxi64=24.2.1 git build-essential
git clone https://github.com/tarwirdur/fb_st7796s.git
cd fb_st7796s/kernel_module/
make
make install
depmod -A
echo "fb_st7796s" >> /etc/initramfs-tools/modules
update-initramfs -u
cd ../dts/
armbian-add-overlay sun50i-h616-st7796s.dts
```
