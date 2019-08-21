# Raspbian installation notes

The following sections provide instructions on how to install and configure [Raspbian](https://www.raspbian.org/) on the
Raspberry Pi 3 (Model B). The installation uses the minimal image of Raspbian (_Raspbian Buster Lite_) available at the Raspberry official website in section _Downloads_ (see [link](https://www.raspberrypi.org/downloads/raspbian/)).

## Wireless configuration

[wpa_supplicant](http://w1.fi/wpa_supplicant/) is installed and started by default. In order to connect to an existing
wireless network, use the `wpa_cli` CLI command with root privileges. Follow the commands listed herein and don't forget
to save the configuration before you exit from `wpa_cli`.

```bash
$ sudo wpa_cli
[...]
> add_network
0
> set_network 0 ssid "<MY_NETWORK_SSID>"
OK
> set_network 0 psk "<MY_NETWORK_PASSWORD>"
OK
> enable_network 0
[...]
> save_config
```

## Enabling SSH

To enable the SSH server use the Raspbian utility `raspi-config`. From the menu, follow the path _5 Interfacing Options_
&rarr; _P2 SSH_ to start the SSH server.

## Create a new user

Your minimal setup of the Raspberry Pi might require a new user. Use the interactive command `adduser` to create a user
named _<NEW_USER>_:

```bash
$ sudo adduser <NEW_USER>
```

Then add _<NEW_USER>_ to all the groups that also `pi` is member of. Use `usermod` following the example below:

```bash
$ sudo usermod \
    --groups adm,dialout,cdrom,sudo,audio,video,plugdev,games,users,input,netdev,gpio,i2c,spi \
    <NEW_USER>
```
