# Raspberry Pi

#### Headless installation via WiFi/SSH

1. Flash Raspbian image:
   ```
   sudo dd if=<image-file>.img of=<device-listed-with-lsblk> bs=4M conv=fsync status=progress
   ```
2. Empty file `ssh` on boot partition
3. File `wpa_supplicant.conf` on boot partition, containing:
   ```
   country=US # Your 2-digit country code
   ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
   network={
       ssid="YOUR_NETWORK_NAME"
       psk="YOUR_PASSWORD"
       key_mgmt=WPA-PSK
   }
   ```

#### Standard user:

- Username: `pi`
- Password: `raspberry`

#### Easy configuration (VNC, SSH, Hostname, Language)

```$ sudo raspi-config```

#### Update

```$ sudo apt-get update && sudo apt-get upgrade -y```

#### Autostart script in terminal on boot

Create script `script.sh` and make it executable:

```$ chmod +x script.sh```

Put `$SHELL` at the end of the script so it doesn't close after finishing (or error).

To make it run at startup:

```
$ cd /etc/xdg/autostart
$ sudo nano <name>.desktop
    [Desktop Entry]
    Type=Application
    Name=Some-String
    Comment=Some String
    Exec=lxterminal -e /path/to/script.sh
$ sudo chmod +x <name>.desktop
```
