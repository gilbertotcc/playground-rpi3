# Raspbian Installation Notes

## Wireless configuration
`wpa_supplicant` is already running by default.

To connect to an existent wireless network and then save the
wpa_supplicant configuration:

````
# wpa_cli
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
````
