# Initial/Static Setup

1. I connected the router to the switch through the Ethernet port

2. I connected all the Office equipment, except for the laptop, to the switch

3. I connected the wireless router (WRT300N) to the switch. I initially asked whether I should connect the switch to the Internet (WAN) port or one of the Ethernet (LAN) ports. After researching, I found that there are two main options:
    
   A) If the WRT300N is used as a full router, I should connect the Internet (WAN) port to the switch. This creates a separate subnet, with the WRT300N acting         as its own DHCP server and gateway.

   B) If the goal is to use it as a wireless access point (AP) — extending the main wired network without routing — I should connect one of the LAN (Ethernet)         ports to the switch, disable its DHCP server, and assign it a static IP in the same range (e.g., 192.168.1.2).

![[image 1]]
