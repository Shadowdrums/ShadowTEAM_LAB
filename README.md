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

- Motherboard: B550M AORUS PRO-P
- CPU: AMD Ryzen 7 5700X (8-core, SMT)
- RAM: 64GB DDR4 (Trident Z Royal, 4x16GB, 3600MT/s)
- Storage:
- 1TB WD Black SN770 M.2 NVMe SSD
- 2x 1TB WD Black HDDs in RAID 1
- GPU: Zotac Geforce 3060 RTX OC 12GB VRAM
- Power Supply: Corsair 850W
- Be Quiet! Tower cooler
- 7 case fans

### High Computing Power

The AMD Ryzen 7 5700X 8-core CPU with Simultaneous Multi-Threading (SMT) offers an impressive amount of processing power, further complemented by a substantial 64GB of DDR4 RAM (Trident Z Royal, 4 16GB 3600MT/s RAM Cards), and powered by a 850W powersupply offering plenty 
of power.

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

## Additional Servers

### Testing Server

#### Specifications
- **Motherboard:** M-ATX Gigabyte GA-B150M-D3H
- **CPU:** Intel Core i5-6500 (4 cores) 3.6GHz
- **RAM:** 16GB (2x8GB 2400MT/s Corsair)
- **GPU:** NVIDIA Tesla K40c 12GB
- **Storage:** 1 TB WD Blue SA510 2.5" SATA3 SSD
- **Power Supply:** EVGA 650W
- **Case:** Open Mining Case
- **Cooling:** Deepcool Digital-temperature-display Tower Cooler
- **Operating System:** Linux Ubuntu 22.02.3-Server-x86x64-amd64

##### Use Case:
This server functions as a test bench before moving on to the other servers for production and application. The CPU has had a slight overclock for a 9.69% performance boost. It is crucial for testing and validating applications before deployment.

### GPU-AI-Server

#### Specifications
- **Motherboard:** ASUSTeK PRIME B550-PLUS AC-HES
- **CPU:** AMD Ryzen 5 3600 (6 cores) @ 3.600GHz
- **RAM:** 64GB (T-Force Vulcan Z DDR4 3200MT/s), 4x16GB RAM Cards
- **Storage:** 1 TB WD Blue SA510 2.5" SATA3 SSD
- **GPU:** Gigabyte RTX 4060 OC (overclocked) 8GB Low Profile
- **GPU2** Gigabyte GT 1030 (for GUI & troubleshooting)
- **Expansion** dual port ethernet PCI-e expansion card (motherboard did not support Wake on LAN but supported Wake on PCI-e so expansion card is used more main netowrking and WoL)
- **Power Supply:** ThermalTake 750W
- **Cooling:** BeQuiet! Pure Rock 2 Tower Cooler
- **Case:** Open mining case for ease of access
- **Operating System:** Ubuntu Server 22.02 OS

##### Use Case:
This server is dedicated to developing AI and other software that requires GPU acceleration. It significantly accelerates AI model training and other GPU-intensive tasks, contributing to faster development cycles.

### Super Pi (Main Server)

#### Specifications
- **CPU:** Broadcom BCM2711, Quad-core Cortex-A72 (ARM v8 64-bit SoC) @ 1.5GHz
- **RAM:** 8GB LPDDR4-3200 SDRAM
- **Boot Device:** 128GB Sandisk Extreme micro SD
- **Storage:** 1TB SATA3 M.2 SSD
- **Case:** Pironman pi tower case with M.2 HAT and system health display
- **Cooling:** Mini tower cooler with Noctua 40x40x10mm case fan
- **Operating System:** kali linux purple (Customized)

##### Use Case:
The Super Pi serves as the main server and the primary gateway into the home lab network via SSH for all devices. It handles various tasks such as file storage, backup management, and network administration. Its SSH capabilities allow secure access to other servers and devices within the network.

### Network Storage Configuration

All servers, including the Super Pi, are configured as network-attached storage (NAS) devices for the main desktop. This setup is utilized for backing up files on external drives, providing redundancy and secure backups.

## Pi Router

### Purpose and Benefits

This custom router project was created with the primary goal of establishing a separate network dedicated to handling external SSH traffic. This setup offers several advantages:

- **Enhanced Security**: By segregating external SSH traffic from the main local network, you create an additional layer of security, minimizing potential risks associated with direct access to sensitive systems.

- **Optimized Network Performance**: Allocating a dedicated network for SSH traffic ensures that it doesn't compete with other activities on the main network, resulting in smoother, more reliable connections.

- **Isolation of Services**: The isolated network allows you to manage and monitor SSH connections separately, making it easier to identify and respond to any unusual activity.

- **Flexibility and Control**: This setup provides you with greater control over SSH access, allowing for specific configurations tailored to your needs.

### Project Overview

This project showcases the creation of a custom router using a Raspberry Pi 4B with 2GB of RAM, running the powerful OpenWRT operating system. This setup leverages the Raspberry Pi's capabilities alongside OpenWRT's robust networking features. It makes use of a Cana Kit external WiFi adapter for broadcasting a WiFi signal. Additionally, the internal WiFi card of the Pi connects to the main router for internet access. For wired connections, a 5-port unmanaged TP-Link Ethernet switch is integrated. To regulate temperature, a fan is included within the custom case. The Pi router is securely mounted on top of the switch using Velcro. Furthermore, a Pico W is Velcroed to the top of the router, providing essential functionality.

### Key Features

- **Hardware**:
  - Raspberry Pi 4B (2GB)
  - Cana Kit external WiFi adapter
  - 5-port unmanaged TP-Link Ethernet switch
  - Case with integrated fan
  - Raspberry Pi Pico W

- **Wireless Capabilities**:
  - The Cana Kit adapter enables the broadcast of a WiFi signal.
  - The Pi's internal WiFi card establishes a connection to the main router for internet access.

- **Wired Networking**:
  - A 5-port TP-Link switch provides reliable wired connections for devices.

- **Temperature Regulation**:
  - A dedicated fan is integrated into the custom case, ensuring optimal operating temperatures.

- **Secure Mounting**:
  - The Pi router is securely attached to the TP-Link switch using Velcro strips.
  - A Pico W is Velcroed on top of the router, enhancing its capabilities.

- **Pico W Keep-Alive**:
  - The Pico W is connected to the Pi router via its internal WiFi card. It serves as a keep-alive mechanism for the SSH server, ensuring continuous connectivity even in the event of network disruptions.

## Additional Considerations

- **Network Configuration**
- All servers in the home lab run off the network managed by the Pi router, providing centralized control and security.
  
- Keep the system updated with the latest security patches to ensure optimal performance and security.
- Regularly monitor the Raspberry Pi's temperature and adjust fan settings if necessary to prevent overheating.

- Both the testing-server and GPU-AI-server have Wake-On-LAN enabled in Bios that users from the main server can use
  to turn on the servers as they need them to extend server life and reduce energy costs.

## Conclusion

To merely label this home lab as a collection of Raspberry Pis and PCs would be a gross simplification. It stands as a cohesive, highly adaptable computing ecosystem crafted with profound insights into hardware, software, networking, and cybersecurity. Whether the need revolves around cybersecurity research, advanced networking, or general-purpose computing, this home lab presents the resources, flexibility, and security to tackle virtually any IT-oriented challenge.

What's birthed here transcends the standard home lab setup. It epitomizes engineering and vision, elevating the home lab concept to unprecedented heights. Through deliberate planning, adept implementation, and a focus on forging a system where the entirety is more significant than the sum of its components, this home lab emerges as a testament to the wonders achievable with contemporary technology and a dash of inventiveness.

## Special Thanks

[DJ Stomp](https://github.com/DJStompZone)
