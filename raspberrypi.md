# TODO

dateien auf boot partition, oberster ordner
 - leere datei "ssh"
 - wpa_supplicant.conf mit inhalt:
country=DE
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
scan_ssid=1
ssid="your_wifi_ssid"
psk="your_wifi_password"
key_mgmt=WPA-PSK
}


standard user: pi
pw: raspberry

standard hostname: raspberrypi

vnc aktivieren/andere einstellungen:
sudo raspi-config

sudo apt-get update && sudo apt-get upgrade -y





## Autostart im Terminal

$ cd /etc/xdg/autostart
$ sudo nano <name>.desktop
    [Desktop Entry]
    Type=Application
    Name=Some-String
    Comment=Some String
    Exec=lxterminal -e /path/to/script.sh
$ sudo chmod +x <name>.desktop

script.sh muss ausführbar sein
$SHELL am ende vom skript macht dass es sich nicht automatisch schließt
