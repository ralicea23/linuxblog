---
author: "Rob Alicea"
title: "A Beginner's Guide to Setting Up Pi-hole with Unbound for Ad Blocking and Enhanced Privacy"
date: "2023-09-19"
ShowReadingTime: True
tags: ["pi-hole", "security", "dns"] 
    
---

![New Linux User](/img/4.png)

# Introduction:

Are you tired of annoying ads cluttering your web browsing experience and concerned about your online privacy? Pi-hole with Unbound might be the solution you've been looking for. In this beginner's guide, we'll walk you through the step-by-step process of setting up Pi-hole with Unbound on your Raspberry Pi or any other compatible device.
What is Pi-hole and Unbound?

Pi-hole is a network-level ad blocker that helps you eliminate unwanted advertisements and trackers from all devices on your network. It acts as a DNS (Domain Name System) sinkhole, which means it intercepts requests to known ad-serving domains and prevents them from loading.

Unbound, on the other hand, is a powerful DNS resolver that enhances your privacy by securely resolving DNS queries locally, without relying on third-party DNS servers. When combined with Pi-hole, it provides an extra layer of privacy and security.
Prerequisites:
    - Hardware: You'll need a Raspberry Pi (any model should work) or a           compatible device to install Pi-hole and Unbound.
    - Operating System: Install Raspberry Pi OS or any other compatible Linux distribution on your device.
    - A Static IP Address: Assign a static IP address to your Raspberry Pi to ensure stable DNS resolution.
    - Basic Command Line Skills: Familiarity with basic Linux terminal commands will be helpful.

# Step 1: Install Pi-hole

Update your system: Open a terminal and run the following commands:
```   
sudo apt update
sudo apt upgrade
```
# Install Pi-hole: Run the following command and follow the on-screen instructions to install Pi-hole:
```
curl -sSL https://install.pi-hole.net | bash
```
Configure Pi-hole: During the installation, you'll be prompted to set a password and choose your upstream DNS provider. You can either use the default or select one that suits your needs.

Note down your Admin Console URL: After the installation is complete, make sure to note down your Pi-hole Admin Console URL. It will look something like http://pi.hole/admin.

# Step 2: Configure Your Router

To ensure all devices on your network use Pi-hole for DNS resolution, log in to your router's settings and set the DNS server to the static IP address of your Raspberry Pi.

# Step 3: Install Unbound

Install Unbound: Open a terminal and run the following command to install Unbound:
```
sudo apt install unbound
```
# Configure Unbound: Edit the Unbound configuration file by running:
```
sudo nano /etc/unbound/unbound.conf.d/pi-hole.conf
```
Add the following lines to the file:
```
server:
   do-not-query-localhost: no
   interface: 127.0.0.1
   access-control: 192.168.1.0/24 allow
```
Replace 192.168.1.0/24 with your local network's CIDR notation.

Restart Unbound: Restart the Unbound service to apply the changes:
```
    sudo service unbound restart
```
# Step 4: Test Your Setup

Test Pi-hole: Open a web browser and visit any website with ads. You should notice a significant reduction in ad content.

Check Unbound: Verify that Unbound is working by running the following command:
```
    dig @127.0.0.1 example.com
```
You should see a response from your local Unbound DNS resolver.

Congratulations! You've successfully set up Pi-hole with Unbound, enhancing your online privacy and blocking ads across your entire network. Enjoy a faster, cleaner, and more secure browsing experience. Remember to periodically update Pi-hole's blocklists for the best ad-blocking performance.

![New Linux User](/img/logo.svg)


