<h1 align="center">Bluetooth +</h1>
<p align="center">bluetooth deauther with automation.</p><br>

## Features
**Device Scanning:**
- Uses the hcitool scan command to detect nearby Bluetooth devices.
- Displays a list of discovered devices with their MAC addresses and names.
- Allows the user to select a target device by index.

**Attack Configuration:**

Prompts the user for the size of packets to send.
Provides a choice between two attack types:
Ping Flood (l2ping): Sends continuous ping packets to the target.
Connection Flood (rfcomm): Sends repeated connection requests to the target.

**Automation:**
        Automatically injects the selected device's MAC address into the attack command.
        Loops indefinitely to continue the attack until manually stopped.

## Script Overview

**The script consists of two main parts:**

Device Discovery:
        The function find_devices scans for Bluetooth devices and provides a list for user selection. The selected device's MAC address is used as the attack target.

Attack Execution:
        The user provides the packet size and selects the attack type.
        Based on the user's choices, the script constructs the appropriate attack command (l2ping or rfcomm) and executes it in a loop.

## How to Use

**Clone the Repository:**
```
git clone https://github.com/mavaaq/bluetooth-deauthenticator.git
```
```
cd bluetooth-deauthenticator
```

  

## Run the Script:

```
sudo bash bluetooth_attack.sh
```


Follow the Prompts:
- The script will scan for nearby Bluetooth devices.
- Select the target device by entering its index from the list.
- Specify the packet size and choose an attack type.

Monitor the Attack:
- The script will continuously send packets to the selected target.
- Press Ctrl+C to stop the attack.

## Requirements

- Linux system with Bluetooth support.
- BlueZ tools installed:

```
sudo apt-get install bluez
```

Run the script with proper permissions (e.g., sudo).

## Example Output

    [*] Scanning for Bluetooth devices nearby...
    [*] Devices found:
    0) 00:1A:7D:DA:71:13 - Device_1
    1) 00:1B:63:84:45:E6 - Device_2
    [?] Enter the number of the device you want to target: 1
    [+] Selected device: 00:1B:63:84:45:E6
    [?] Enter the packet size (e.g., 128): 256
    Attack types:
        1) l2ping - Ping flood
        2) rfcomm - Connect flood
    [?] Select the attack type (1 or 2): 1
    Bluetooth deauthenticator v0.2.0-alpha
    [*] Starting attack on 00:1B:63:84:45:E6 -- Packet size: 256 -- Attack type: 1
    [+] Packet sent to 00:1B:63:84:45:E6 -- Packet size: 256 -- Attack type: 1

## Important Notes

Educational Purposes Only: This script is intended for research, testing, and educational purposes. It should only be used in environments where you have explicit permission to test devices.
Ethical Use: Unauthorized use of this script to disrupt or harm devices is illegal and unethical. Always comply with local laws and regulations.

## Contributions

Feel free to open issues or submit pull requests to improve the script. Contributions are welcome, whether it's fixing bugs, optimizing the script, or adding new features.
License

This project is licensed under the MIT License. See the LICENSE file for more details.
Disclaimer

The creators of this script are not responsible for any misuse or damage caused by the tool. Use it responsibly and only in authorized environments.
