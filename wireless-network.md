# Setting up the wireless network

## Switch ARRIS SBG6580 cable modem to bridge mode

1. Factory reset the modem by pressing into the little hole in the back.
1. Connect to modem using an ethernet cable and turn off the wireless radio. Select Wireless > 802.11 Radio > Wireless Radio Enable > Disabled.
1. Switch to bridge mode. Select Basic > Setup > Gateway Mode > Bridged.
1. Reboot the modem.
1. Make sure you can still log into the model at `192.168.100.1`. 

Source: [Bridge Mode Guide | SBG6580](https://routerguide.net/motorola-surfboard-sbg6580-bridge-mode-guide/)

## Setup TP-Link Archer C7 wireless router

1. Connect an ethernet cable from the router to port 1 of the modem.
1. Change the IP address. Enter a custom value for Network > LAN > IP address (make sure it isn't `192.168.100.1`, which is used by the modem when it's in bridge mode).
1. Change the name of the 2.4GHz network. Enter a value for Wireless 2.4GHz > Wireless Settings > Wireless Network Name.
1. Change the password for the 2.4GHz network. Enter a value for Wireless 2.4GHz > Wireless Security > WPA/WPA2 - Personal(Recommended) > PSK Password.
1. Change the name of the 5GHz network. Enter a value for Wireless 5GHz > Wireless Settings > Wireless Network Name.
1. Change the password for the 5GHz network. Enter a value for Wireless 5GHz > Wireless Security > WPA/WPA2 - Personal(Recommended) > PSK Password.
1. Change admin password. Fill out the form at System Tools > Password.
1. Reboot the router by clicking Systems Tools > Reboot > Reboot.
1. Log into the router again.
1. Click on Quick Setup > Next. 
1. Go through each step of the installation wizard. You may need to reboot your modem as part of the process.

## Notes

You do not need to plug an ethernet cable into your modem to access its admin interface. Simply open a browser and visit `192.168.100.1`.

I've noticed a tendency for the 5GHz network to inexplicably revert to a default name (e.g. TP-LINK_XXXX). This will cause all clients to be disconnected from the network. To restore the network, you have to restart the router (Systems Tools > Reboot > Reboot).
