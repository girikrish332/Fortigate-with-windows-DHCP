# Cisco Switch VLAN Configuration README

## Overview
This README provides instructions for configuring VLANs on a Cisco switch (SW1). VLANs (Virtual Local Area Networks) are used to segment network traffic for better organization, security, and efficiency.

## Configuration Steps
Follow these steps to configure VLANs on your Cisco switch:

1. **Access the Switch:** Use a terminal emulator (e.g., PuTTY) to access the switch's command-line interface (CLI).

2. **Enter Configuration Mode:**
en config t
markdown

3. **Hostname Configuration:**
hostname SW1
markdown

4. **VLAN Configuration:**
vlan 10 
name vlan10 
no sh 
exit
vlan 20 
name vlan20 
no sh 
exit
vlan 30 name 
vlan30 
no sh 
exit
markdown

5. **Access Port Configuration (VLAN 10):**
interface range g0/0 - 3 
switchport mode access 
switchport access vlan 10 
no sh 
exit
markdown

6. **Access Port Configuration (VLAN 20):**
interface range g1/0 - 3 
switchport mode access 
switchport access vlan 20 
no sh 
exit
markdown

7. **Trunk Port Configuration (VLAN 10, 20):**
interface g3/3 
switchport mode trunk encapsulation dot1q 
switchport mode trunk 
switchport trunk allowed 
vlan 10,20 
no sh 
exit
markdown

8. **SVI Configuration (VLAN 30):**
interface vlan 30 ip address 192.168.30.1 255.255.255.0 
no sh 
exit
vbnet

9. **Save Configuration:**
After completing the configuration, save the changes to the switch's startup configuration to ensure they persist across reboots:
copy running-config startup-config
vbnet

## Configuration Verification
After configuring VLANs, you can verify the configuration using the following commands:

- `show vlan`: Displays VLAN information.
- `show interfaces status`: Shows interface status and VLAN membership.
- `show interfaces trunk`: Shows trunking information for all interfaces.
- `show ip interface brief`: Displays interface IP address information.

## Additional Resources
For more information on Cisco switch VLAN configuration and troubleshooting, refer to the Cisco documentation or consult Cisco's technical support resources.

## Notes
- Double-check the VLAN configurations and interface assignments to ensure they match your network requirements.
- Take caution when making changes to the switch's configuration to avoid disrupting network connectivity.
Feel free to modify this README file as needed to suit your documentation preferences or specific environment.

