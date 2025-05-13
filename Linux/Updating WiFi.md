### **Using the Command Line**

1. **Edit the Configuration File:**
    - Open a terminal and edit the network's configuration file:
    ```
    `sudo nano /etc/NetworkManager/system-connections/<network-name>.nmconnection
    ```
    - Replace `<network-name>` with the name of your WiFi network.

2. **Update the Password:**
       - Look for the line starting with `psk=` under the `[wifi-security]` section.
    - Update it with your new password:
        ```
        psk=newpassword
        ```

3. **Save and Exit:**
       - Press `Ctrl+O` to save the file and `Ctrl+X` to exit the editor.
    
4. **Restart Network Manager:**
    
    - Restart the network service to apply changes:
        ```
        sudo systemtl restart NetworkManager
        ```

5. Reconnect
	- The system should automatically reconnect using the updated credentials.