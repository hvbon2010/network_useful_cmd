# network_useful_cmd
## Wifi commands
### Scan network
`iw wlan0 scan`

### Setup wifi network via wpa_supplicant.conf
`wpa_passphrase <WIFI-SSID> <PASSWORD> > wpa_supplicant.conf`

### Connect to specified wifi in wpa_supplicant.conf
`wpa_supplicant -B -c wpa_supplicant.conf -i wlan0`

### Aquire an ip address for wlan0
`dhcpcd wlan0`

### Disconnect wifi
`wpa_cli -i wlan0 disconnect`
Or
`start-stop-daemon -K -n wpa_supplicant`

### Connect to the new network
```
start-stop-daemon -K -n wpa_supplicant
wpa_passphrase <NEW-WIFI-SSID> <NEW-PASSWORD> > wpa_supplicant.conf
wpa_supplicant -B -c wpa_supplicant.conf -i wlan0
```

### Get wlan0 information
`iwconfig wlan0`
