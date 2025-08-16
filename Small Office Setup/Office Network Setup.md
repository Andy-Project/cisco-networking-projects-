# Initial

- Cisco 1941 Router → Switch
    - Connected GigabitEthernet0/0 → FastEthernet0/1 on switch.

- Office Equipment → Switch
    - All PCs, printers, and other devices are connected except for the laptop.

- Wireless Router (WRT300N) → Switch

    Two options:

  1. Router Mode (Separate Subnet)

        - Connect WAN port → switch

        - WRT300N acts as router + DHCP server

        - Creates a separate subnet (e.g., 192.168.2.x)

    2. Access Point Mode (Same Subnet) 

        - Connect LAN port → switch

       - Disable DHCP
    
       - Assign static IP (e.g., 192.168.1.2)

       - Extends the main network without routing

I decided the WRT300N router would be an access point. 

![Logical topology](images/image1.jpg)


# Assign IP Addresses & Configure Subnetting

- Cisco 1941 Router → Switch

    - Interface: GigabitEthernet0/0 → Switch FastEthernet0/1

    - IPv4 Address: 192.168.1.1 (Class C private IP)

    - Subnet Mask: 255.255.255.0

    - CLI Command: no shutdown (enable interface)

Role: Default gateway for all devices on the 192.168.1.0/24 network

![1941 Router](images/image2.jpg)

Learning Note:
- 192.168.1.1 is a Class C private IP address. The router is usually assigned the first IP address, and other devices receive addresses such as 192.168.10, etc. I learned that Class C is more common (many consumer routers use this range by default) since it provides 254 usable IP addresses, which is plenty for most small offices/home networks. While using another class, like A, is possible, it’ll waste IPs. You get a huge number of IP addresses (over 16 million usable in 10.0.0.0/8), which is overkill for a small office.


- After setting up the router, I manually assigned each device:
    - its own IP
    - the subnet mask
    - the default gateway of the 1941 router.

| Device   | IP Address     | Subnet Mask      | Default Gateway |
|----------|---------------|----------------|----------------|
| PC 0     | 192.168.1.10  | 255.255.255.0  | 192.168.1.1    |
| PC 1     | 192.168.1.11  | 255.255.255.0  | 192.168.1.1    |
| PC 2     | 192.168.1.12  | 255.255.255.0  | 192.168.1.1    |
| PC 3     | 192.168.1.13  | 255.255.255.0  | 192.168.1.1    |
| PC 4     | 192.168.1.14  | 255.255.255.0  | 192.168.1.1    |
| Printer  | 192.168.1.20  | 255.255.255.0  | 192.168.1.1    |
| Server   | 192.168.1.100 | 255.255.255.0  | 192.168.1.1    |

- Interface of PC0

![PC0-Static](images/image3.jpg)


With everything set up, I need to:
- Verify that all devices can communicate with the default gateway (Cisco 1941 router) and the printer.  
- Method: Used the `ping` command from each PC to test connectivity.

PC0 pinging the router:

```
ping 192.168.1.1

Pinging 192.168.1.1 with 32 bytes of data:
Request timed out.
Request timed out.
Reply from 192.168.1.1: bytes=32 time<1ms TTL=255
Reply from 192.168.1.1: bytes=32 time=4ms TTL=255

Ping statistics for 192.168.1.1:
    Packets: Sent = 4, Received = 2, Lost = 2 (50% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 4ms, Average = 2ms
```
