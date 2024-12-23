# ESP32 wifi hacker

Capture wifi handshake using esp32 mcu

<img src="https://github.com/xiv3r/ESP32-wifi-hacker/blob/main/esp32_1.png">


# Installation
> Download the firmware

| Name            | Offset |
|-----------------|--------|
| [bootloader](https://raw.githubusercontent.com/xiv3r/ESP32-wifi-hacker/refs/heads/main/bin/bootloader.bin)      | 0x1000 |
| [partition table](https://raw.githubusercontent.com/xiv3r/ESP32-wifi-hacker/refs/heads/main/bin/partition-table.bin) | 0x8000 |
| [firmware](https://raw.githubusercontent.com/xiv3r/ESP32-wifi-hacker/refs/heads/main/bin/firmware.bin)        | 0x10000|

# Flash the Firmware

- For Linux
> First install the ESP32 ch340g/cp2102 driver
  - Auto install
```
wget -qO- https://raw.githubusercontent.com/xiv3r/ESP32-wifi-hacker/refs/heads/main/linux | sudo sh
```
  - Manual install
```
pip install esptool
sudo apt install esptool
```
```
esptool -b 115200 --before default_reset --after hard_reset --chip esp32 write_flash --flash_mode dio --flash_freq 20m --flash_size detect 0x1000 bootloader.bin 0x8000 partition-table.bin 0x10000 firmware.bin
```

<br><br>

- For Windows

  - First install the ESP32 ch340g/cp2102 driver
  - Download the [Flash download tools](https://github.com/xiv3r/ESP32-wifi-hacker/releases/download/Flasher/flash_download_tool.zip)
  - import the firmware to the flash download tool
  - bootloader `0x1000`
  - partition  `0x8000`
  - firmware   `0x10000`

<img src="https://github.com/xiv3r/ESP32-wifi-hacker/blob/main/esp32_win.png">

# Bruteforce the Handshake (.hccapx) | Android
- Termux kali nethunter rootless
```
sudo apt install aircrack-ng -y
```
- > import the handshake to storage/downloads
- > download any wordlist
```
termux-setup-storage
```
```
cd storage/downloads
```
```
aircrack-ng handshake.hccapx -w rockyou.txt
```

# HashSuiteDroid | Android

- Download the [HashSuiteDroid](https://github.com/xiv3r/ESP32-wifi-hacker/releases/download/Flasher/HashSuiteDroid_1_6.apk)
- Import the handshake and wordlist
