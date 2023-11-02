# ShadowTEAM_LAB
# Ultimate Home Lab

A Masterclass in Computing and Networking

_By: Shadowdrums_

![Static Badge](https://img.shields.io/badge/Runs%20On-Coffee-6f4e37?style=for-the-badge&logo=coffeescript&logoColor=ffffff&labelColor=613B19)

## Introduction

Welcome to a guided tour of one of the most comprehensive and advanced home lab setups you'll likely encounter. Designed with meticulous attention to detail and an evident depth of understanding of computing, networking, and cybersecurity, this home lab serves as a practical, educational, and experimental platform for a myriad of I.T. disciplines.

## Raspberry Pi Cluster: The Backbone

**Trio of Raspberry Pi 4 Model B with 8GB RAM**

The cluster includes three Raspberry Pi 4 Model B devices, each boasting 8GB of RAM. One of these serves as the main external SSH connection server running Kali Linux Purple. This primary SSH server acts as a gateway, enabling users to connect to the other Raspberry Pis, including one running Ubuntu that serves as a general-purpose server, and another that is the powerhouse "Super Pi."

### Advanced SSH Tunneling and Networking

The intricacy of the SSH tunneling is worth noting. An external SSH connection targeting a 5-digit port on the main router is forwarded to a 4-digit port on a specialized Raspberry Pi 4 Model B with 2GB RAM running OpenWRT. This Raspberry Pi then forwards the connection to the main SSH server on port 22, creating a multi-layered, secure tunnel into the home lab network.

### Specialized Roles for Each Pi

Each Raspberry Pi in the cluster is purpose-built to perform a specialized function. From SSH tunneling, routing via OpenWRT, to server roles on Ubuntu and Kali Linux, the system's modular approach not only makes management easier but also ensures efficient resource utilization.

### The "Super Pi"

Among these devices is the standout "Super Pi"—a Raspberry Pi equipped with 8GB of RAM and a 1TB SATA3 M.2 SSD. It's not just a Pi; it's a miniature powerhouse designed to handle data-intensive tasks and computational operations that would traditionally necessitate a full-scale server.

### Monitoring and Reliability

A Raspberry Pi Pico W is seamlessly integrated into the system to monitor its health. This microcontroller pings the servers every 3 minutes as a "keep-alive," ensuring uninterrupted and efficient operations.

### Power and Cooling

The individual 20W power supplies and cooling solutions for each Raspberry Pi highlight a meticulous attention to detail, emphasizing longevity and optimal performance.

## Main Desktop: The Control Center

### High Computing Power

The AMD Ryzen 5 6-core CPU with Simultaneous Multi-Threading (SMT) offers an impressive amount of processing power, further complemented by a substantial 64GB of DDR4 RAM.

### Diverse Storage Options

The WD Black SN770 1TB M.2 NVMe SSD ensures rapid access to frequently used data. Additionally, two 1TB WD Black HDDs in a RAID 1 (mirroring) configuration offer ample storage space with enhanced performance and redundancy.

### Graphics and Cooling

The Zotac Geforce 3060 RTX GPU affords the potential for GPU-accelerated computing tasks. Coupled with seven case fans and a tower cooler, this guarantees that every component maintains optimal temperature ranges.

## Laptop as Direct-Attached Storage (DAS) and Windows Server

### Secondary Server

Sporting a 4-core CPU, 16GB of RAM, and 500GB storage, this laptop doubles as a Direct-Attached Storage (DAS) device and a host for a Windows sandbox server, which allows for isolated testing and experimentation.

### Unique Network Architecture

While the Raspberry Pis connect to their dedicated router, the main desktop links to the primary household router. The laptop, functioning as DAS, is integrated into the Raspberry Pi network. An Ethernet connection between the main desktop and the laptop establishes a direct link, enabling high-speed data transfers and smooth interactions across the two distinct network environments.

### Operating Systems

#### Windows 10 Pro

Windows 10 Pro runs on both the desktop and the laptop, enhancing the home lab's capabilities. Features such as BitLocker, advanced Windows Defender functionalities, and Hyper-V for virtualization transform these Windows machines into powerful extensions of an already advanced home lab setup.

#### Raspberry Pi Operating Systems

The Raspberry Pis operate on Kali Linux, Ubuntu, and OpenWRT, each tailored to their specific roles, further adding to the system's adaptability and specialized nature.

## Conclusion

To merely label this home lab as a collection of Raspberry Pis and PCs would be a gross simplification. It stands as a cohesive, highly adaptable computing ecosystem crafted with profound insights into hardware, software, networking, and cybersecurity. Whether the need revolves around cybersecurity research, advanced networking, or general-purpose computing, this home lab presents the resources, flexibility, and security to tackle virtually any IT-oriented challenge.

What's birthed here transcends the standard home lab setup. It epitomizes engineering and vision, elevating the home lab concept to unprecedented heights. Through deliberate planning, adept implementation, and a focus on forging a system where the entirety is more significant than the sum of its components, this home lab emerges as a testament to the wonders achievable with contemporary technology and a dash of inventiveness.

## Special Thanks

[DJ Stomp](https://github.com/DJStompZone)
