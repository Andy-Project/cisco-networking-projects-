# Initial/Static Setup

1. I connected the 1941 router to the switch through the Ethernet port

2. I connected all the Office equipment, except for the laptop, to the switch

3. I connected the wireless router (WRT300N) to the switch. I initially asked whether I should connect the switch to the Internet (WAN) port or one of the Ethernet (LAN) ports. After researching, I found that there are two main options:

    A) If the WRT300N is used as a full router, I should connect the Internet (WAN) port to the switch. This creates a separate subnet, with the WRT300N         acting as its own DHCP server and gateway.

    B) If the goal is to use it as a wireless access point (AP) — extending the main wired network without routing — I should connect one of the LAN                 (Ethernet) ports to the switch, disable its DHCP server, and assign it a static IP in the same range (e.g., 192.168.1.2).

![Image1](https://github.com/user-attachments/assets/584e3c4b-776b-4ee5-878e-f0f2fd119f37)

# Assign IP Addresses & Configure Subnetting

1. I began by configuring the Cisco 1941 router, which will serve as the default gateway for all devices on the network. To this I:

A) Navigated to: Config > Interface > GigabitEthernet0/0
        - The router is connected from its GigabitEthernet0/0 port to the FastEthernet0/1 port on the switch.
      
 B) Assigned the IPv4 Address: 192.168.1.1

192.168.1.1 is a Class C private IP address. The router is usually assigned the first IP address, and other devices receive addresses such as 192.168.10, etc. I learned that Class C is more common (many consumer routers use this range by default) since it provides 254 usable IP addresses, which is plenty for most small offices/home networks. While using another class, like A, is possible, it’ll waste IPs. You get a huge number of IP addresses (over 16 million usable in 10.0.0.0/8), which is overkill for a small office.

C) Subnet Mask: 255.255.255.0

D) Enabled the interface by typing in “no shutdown” in the CLI (turned the port ON)

This configuration makes the router the central point of communication for all connected devices within the 192.168.1.0/24 network.
![image2](https://github.com/user-attachments/assets/8c429035-6c52-401d-b7e0-7d622a300c57)

2. 
