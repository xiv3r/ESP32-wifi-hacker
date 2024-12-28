# CH340G_SER linux driver install

- Dependencies
```
sudo apt update
sudo apt install make cmake bc build-essential unzip -y
sudo apt install linux-image-$(uname -r|sed 's,[^-]*-[^-]*-,,')
sudo apt install linux-headers-$(uname -r|sed 's,[^-]*-[^-]*-,,')
```
```
sudo -i
wget https://github.com/xiv3r/ESP32-wifi-hacker/raw/refs/heads/main/drivers/CH341SER_LINUX.ZIP && unzip CH341SER_LINUX.ZIP && cd CH341SER_LINUX/driver && make && sudo make load && sudo make install
```
