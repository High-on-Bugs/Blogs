---
title: "Setting Up My Simple Home Server: A Practical Guide"
datePublished: Sun Jan 14 2024 10:24:26 GMT+0000 (Coordinated Universal Time)
cuid: clrdcn6vp000209jxc68e8vgi
slug: setting-up-my-simple-home-server-a-practical-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705227618720/4fd18848-3721-46d1-b931-686e85314423.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1705227834764/e73044cf-040d-4a4d-bc7e-b88af0ad59c5.avif
tags: ubuntu, server, debian, media, nas-storage-solutions

---

## **Chapter 1: Formatting the Old PC**

### **Introduction**

Welcome to the kickoff of my home server project! Imagine this: this forgotten PC, originally my dad's ex-workstation, is sitting idle. Armed with an Intel i3 8th gen processor, no flashy GPU, and a humble 8 gigs of RAM, I saw potential in turning it into a nifty home server.

**The Appeal of Repurposing**

Repurposing would let me use the home server to back up files, stream movies and media, deploy my projects, and learn some other cool stuff

### **Backing Up Data**

**Importance of Data Backup**

There were not a lot of files to be backed up. So I used Google Drive to back a few of them up. The rest would get purged.

## **Chapter 2: Clean Slate**

**The Decision to Start Fresh**

The chapter culminates in the decision to wipe the slate clean by formatting the existing Windows 10 installation. Reasons behind this choice include eliminating unnecessary clutter, ensuring a fresh start, and optimizing the system for its new role as a home server.

As there was a single SSD, with multiple partitions, I combined them into one and went ahead with the Linux Installation.

This video should be enough to get the steps on how to reset your Windows 10/11 machine:

%[https://www.youtube.com/watch?v=5OVwQdfUztU] 

## **Chapter 3: Journey to Ubuntu Installation**

For Video guidance, you can use this video:

%[https://www.youtube.com/watch?v=oNEwEQ0uU1Y] 

### **Flashing the Drive**

With the old PC prepped and ready, it was time to introduce it to its new companion - a shiny USB drive. I chose to use Balena Etcher for this job, a tool that makes flashing the drive a breeze. A few clicks, and we were set to roll.

### **Navigating the BIOS**

Ah, the backstage BIOS pass to your PC's inner workings. Before diving into the installation, a pitstop in the BIOS was essential. Adjusting settings, ensuring compatibility, and making sure the USB drive took center stage in the boot order.

### **Setting Boot Priority**

The boot priority dance was next on the agenda. I wanted the system to look at the USB drive first, ensuring a smooth transition from the flashing process to the Ubuntu installation.

### **Installation Initiated**

With the USB drive ready and the boot priority set, it was time for the main event - installing Ubuntu. The familiar installation wizard guided me through the process, prompting me for language preferences, time zone settings, and user details. A few clicks later, the installation was underway.

### **No Ethernet Cable, No Problem**

Ah, the hiccup. No Ethernet cable on hand meant no updated packages during installation. But worry not; I opted for a minimal install to keep things straightforward. I would need to set up my internet later.

And there you have it - Chapter 3! The USB drive is flashed, the BIOS is in check, and Ubuntu is making its home on the old PC. Stay tuned for the next chapter, where we tackle connection challenges and navigate the intricacies of USB tethering for internet access during and after installation. 🌐

## **Chapter 4: USB Tethering to Mobile Phone**

### **Overcoming Connection Challenges During Installation**

As the Ubuntu installation progressed, a familiar hurdle emerged – the absence of an Ethernet connection. No Ethernet, no problem - but a solution was in order. This chapter delves into the challenges faced and the journey toward utilizing USB tethering to a mobile phone as the savior.

### **Introduction to USB Tethering**

With no Ethernet cable in sight, the spotlight turned to USB tethering. This technology, often underutilized, allows a seamless connection between a computer and a mobile device, effectively transforming the mobile phone into a gateway to the digital realm.

### **Setting Up IP and Gateway via USB Tethering**

**The Failed Attempt with Manual Net Tools Installation**

Initially, I attempted a manual installation of net tools from the official Ubuntu website. The process involved mounting the tools on a USB drive, but alas, it proved to be a cumbersome task and didn't yield the desired results. It was time to pivot.

**Embracing USB Tethering**

Enter USB tethering - a more straightforward and reliable solution. Connecting the mobile phone to the PC via USB cable initiated the tethering process. A quick check using `ip link` revealed the available network interfaces, among which the USB-tethered interface took center stage.

**Configuring IP and Gateway Settings**

The next step involved setting up the IP address and gateway for the USB-tethered interface. A judicious choice of values ensured a stable internet connection

Let's go through the steps:

1. Check available network interfaces
    
    ```bash
    ip link
    ```
    
2. Recognize the USB interface and assign an IP address manually. Assuming IP as `192.168.42.10/24` and interface as `enp0s20u1`
    
    ```bash
    sudo ip addr add 192.168.42.10/24 dev enp0s20u1
    sudo ip link set enp0s20u1 up
    ```
    
3. Set the default gateway using the following command
    
    ```bash
    sudo ip route add default via 192.168.42.1 dev enp0s20u1
    ```
    
4. Reboot
    
    ```bash
    reboot
    ```
    
5. Try to ping an external IP to confirm if the connection works.
    
    ```bash
    ping 8.8.8.8
    ```
    

*In case of errors, check for Firewall rules*

### **Achieving Internet Access**

With the USB tethering setup, the old PC was now online. Internet access meant that the installation process could proceed without any hiccups.

**Updating Linux and Adding Net Tools**

The newfound internet connection was immediately put to use. The system underwent a thorough update, ensuring that the latest Linux packages were on board. Additionally, the previously elusive net tools were seamlessly added to the arsenal, simplifying future networking tasks.

## **Chapter 5: RTL8812AU Driver Woes**

*Device Name: TP-Link Archer T2U (RTL8812AU)*

### **Dealing with the Absence of an Official Driver**

The path to a fully functional home server encountered a significant hurdle when the built-in Wi-Fi adapter, the TP-Link RTL8812AU, found no official Linux support. Undeterred, I delved into the challenge, determined to find a workaround.

### **Discovering Community Wisdom on Ubuntu Forum**

A ray of hope emerged when I stumbled upon a community post on the Ubuntu forum. Fellow enthusiasts faced similar RTL8812AU woes. The community post led me to a GitHub repository housing a solution to my driver predicament. The repository contained not only the necessary driver files but also somewhat detailed instructions in the README file.

### **Installing the Driver Using Readme Instructions**

After Cloning the repository, I followed the step-by-step instructions from the README file to install the drivers. Commands were entered, configurations were adjusted, and dependencies were resolved, all in alignment with the provided steps. With the driver installed, a quick network restart was in order. The moment of truth arrived as I eagerly awaited the appearance of the Wi-Fi interface, signaling that the RTL8812AU driver had successfully integrated with the system.

The Driver and the steps to install can be found [here](https://github.com/aircrack-ng/rtl8812au).

### **Setting Up Netplan to Configure Networking**

I then configured the network settings using Netplan. This involved crafting a Netplan YAML file, specifying DHCP settings, and nameservers, and providing login credentials for the network. Executing the Netplan YAML file applied the configurations to the system. The digital gears clicked into place as the network settings were adjusted, paving the way for a robust and stable connection.

With Netplan's configurations in place, the once elusive Wi-Fi connection now offered a gateway to the internet. The old PC was now fully equipped, ready to explore the digital landscape and fulfill its role as a reliable home server.

I used this video to get my wifi to work:

%[https://www.youtube.com/watch?v=Dacn58kgMXA] 

My netplan configuration yaml looked as follows:

```yaml
network:
  ethernets:
    enp3s0:
      optional: true
      dhcp4: true
    usb0:
      dhcp4: true
  version: 2
  wifis:
    <interface_name>:
      dhcp4: no
      addresses: [<static_ip_you_want_to_assign>/24]
      routes:
       - to: default
         via: <gateway>
      nameservers:
        addresses: [1.1.1.1, 1.0.0.1]
      access-points:
        <Network_name_SSID>:
          password: <password>
```

## **Chapter 6: Unlocking Advanced Capabilities**

As the home server project unfolded, the quest for enhanced functionalities led to the introduction of several powerful features, turning the old PC into a versatile hub for various applications.

### **SambaShare for NAS**

Embracing the concept of Network-Attached Storage (NAS), the server now boasts SambaShare integration. This enables seamless file sharing across devices within the network. Whether it's documents, media files, or backups, the NAS capabilities provide a centralized repository accessible from any connected device.

Check this video out for help with installation:

%[https://www.youtube.com/watch?v=0-T7af_lRF8&t=945s] 

### **Plex for Media Streaming**

The entertainment dimension received a significant upgrade with the integration of Plex. Now, the server doubles as a media streaming powerhouse. Plex not only organizes the media library but also enables streaming on-demand, turning the old PC into a personal media center.

Check this video out for help with installation:

%[https://www.youtube.com/watch?v=QEP5Tq78cHw] 

### **Docker, Minikube, and OpenSSH for Remote Development**

The journey into the world of containerization began with the installation of Docker. This enables the deployment of applications in isolated containers, ensuring efficient resource utilization and easy management. Minikube, on the other hand, introduces the capabilities of Kubernetes at a smaller scale, providing a robust platform for container orchestration.

Enabling secure remote access for development purposes, OpenSSH was configured. This feature facilitates a secure shell connection, allowing developers to access and manage the server remotely. Coupled with Visual Studio Code's Remote SSH extension, the development workflow is further streamlined, providing a seamless and efficient coding environment.

Check out @[Hitesh Choudhary](@hiteshchoudharylco) and other tutorials on YT to install these!

## Chapter 7: Conclusion

Finally, I'm in a stage where I can shift my entire development workload onto a Linux system to avoid the incessant windows-shaming I've been facing over the years. Having a server ready can also help me get a better grip on computer networks and Linux filesystems as well as learn advanced DevOps topics.

---

If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!