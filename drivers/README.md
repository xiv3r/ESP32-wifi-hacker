# CH340G_SER linux driver install

- Depend
```
sudo apt install cmake bc make wget -y
```
```
wget https://github.com/xiv3r/ESP32-wifi-hacker/raw/refs/heads/main/drivers/CH341SER_LINUX.ZIP && unzip CH341SER_LINUX.ZIP && cd CH341SER_LINUX/driver && make && sudo make load
```
