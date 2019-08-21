# Raspbian installation notes

## Wireless configuration

`wpa_supplicant` is already running by default.

To connect to an existent wireless network and then save the
`wpa_supplicant` configuration:

```bash
$ sudo wpa_cli
[...]
> add_network
0
> set_network 0 ssid "MyNetworkSSID"
OK
> set_network 0 psk "MyNetworkPassword"
OK
> enable_network 0
[...]
> save_config
```

## Enabling SSH

To enable SSH server, `raspi-config` could be used.  To enable the SSH
server from the menu the corresponding entries are "5 Interfacing
Options" -> "P2 SSH".

## Create a new user

```bash
$ sudo adduser new-username
```

```bash
$ sudo usermod \
    --groups adm,dialout,cdrom,sudo,audio,video,plugdev,games,users,input,netdev,gpio,i2c,spi \
    new-username
```
