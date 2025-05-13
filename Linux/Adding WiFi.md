
**See [[Updating WiFi]] to update Wifi password
## **Using `nmcli` (Command Line)**

1. **Scan for Available Networks:**
```
nmcli dev wifi list
```
 This command lists all available WiFi networks.

2. **Connect to the Network:**
```
nmcli dev wifi connect "<SSID>" password "<password>"
```
 Replace `<SSID>` with the network name and `<password>` with the WiFi password.
 
 3. **Verify the Connection:**
```
nmcli dev statu
```
You should see your interface (e.g., `wlan0`) connected to the specified network.