# Wireless Reconnaissance & Packet Capture Lab

## Objective
To passively scan and capture wireless network traffic using monitor mode.
This lab simulates reconnaissance steps a pen tester or network analyst might
take during early engagement.

## Tools Used
  - Kali Linus (VM)
  - Realtek RTL8812AU Wireless Adapter
  - aircrack-ng suite
  - Wireshark

  ## Setup Process
    1. Enable Monitor Mode
      sudo ifconfig wlan0 down  
      sudo airomon-ng check kill
      sudo airomon-ng start wlan0
      sudo ifconfig wlan0 up

    2. Search for 2,4 GHz Networks near device
      sudo airodump-ng --band b wlan0

    3. Focus on a Target Network
      - grab MAC address or BSSID of targeted attack and channel
        -optional to "write" results into a text file 
      - sudo airodump-ng --bssid ____  --channel __ --write text

    4.  Result Analysis in Wireshark
      - Terminate running program
        - open up Wireshark
        - locate .cap file 
        - look at results, filter can be used
