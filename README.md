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
The home lab network now leverages the ASUS RT-AX82U AX5400 Dual-Band WiFi 6 router for enhanced SSH tunneling and networking capabilities. Here's how the updated setup works:

- External SSH Connection: External SSH connections are directed to a high-numbered port on the main household router. The ASUS RT-AX82U, hardwired to the primary router, forwards these connections to the dedicated SSH server (Super Pi) within the home lab.

- Secure Tunneling: The ASUS RT-AX82U provides a robust and secure tunnel for SSH traffic. With advanced QoS and AiProtection Pro features, it ensures that SSH connections are prioritized and protected from external threats.

- Optimized Networking: All servers within the lab are connected to a 5-port TP-Link unmanaged switch, which is hardwired to the ASUS router. This setup minimizes latency and maximizes throughput, making remote access and server management seamless and efficient.

- This updated network configuration offers a significant improvement over the previous Pi Router setup, providing higher speeds, enhanced security, and a more stable connection for all SSH and networking tasks within the lab.

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
- GPU: Gigabyte Geforce RTX 4060 Ti 16GB Vram
- Power Supply: Corsair 850W
- Be Quiet! Tower cooler
- 7 case fans

### High Computing Power

The AMD Ryzen 7 5700X 8-core CPU with Simultaneous Multi-Threading (SMT) offers an impressive amount of processing power, further complemented by a substantial 64GB of DDR4 RAM (Trident Z Royal, 4 16GB 3600MT/s RAM Cards), and powered by a 850W powersupply offering plenty 
of power.

### Diverse Storage Options

The WD Black SN770 1TB M.2 NVMe SSD ensures rapid access to frequently used data. Additionally, two 1TB WD Black HDDs in a RAID 1 (mirroring) configuration offer ample storage space with enhanced performance and redundancy.

### Graphics and Cooling

The Gigabyte Geforce RTX 4060 Ti GPU affords the potential for GPU-accelerated computing tasks. Coupled with seven case fans and a tower cooler, this guarantees that every component maintains optimal temperature ranges.

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
- **CPU:** Intel Core i5-7500 (4 cores) 3.4GHz
- **RAM:** 32GB (T-Force Vulcan Z DDR4 3600MT/s) 2x16GB Ram Cards
- **GPU:** ZOTAC RTX 3060 OC 12GB
- **Storage:** 1 TB WD Blue SA510 2.5" SATA3 SSD
- **Power Supply:** EVGA 650W
- **Case:** Open Mining Case
- **Cooling:** Deepcool Digital-temperature-display Tower Cooler
- **Operating System:** Linux Ubuntu 22.02.3-Server-x86x64-amd64

##### Use Case:
This server functions as a test bench before moving on to the other servers for production and application. It is crucial for testing and validating applications before deployment.

### GPU-AI-Server

#### Specifications
- **Motherboard:** ATX ASUSTeK PRIME B550-PLUS AC-HES
- **CPU:** AMD Ryzen 5 3600 (6 cores) @ 3.600GHz
- **RAM:** 64GB (T-Force Vulcan Z DDR4 3600MT/s), 4x16GB RAM Cards
- **Storage:** 1 TB WD Black SN770 M.2 NVMe SSD
- **GPU:** Gigabyte RTX 4060 OC (overclocked) 8GB Low Profile
- **GPU2** Gigabyte RTX 4060 OC 8GB Low Profile
- **Expansion** dual port ethernet PCI-e expansion card (motherboard did not support Wake on LAN but supported Wake on PCI-e so expansion card is used for netowrking and WoL)
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

# Network Configuration and Router Upgrade
### Introduction
The home lab network has been significantly enhanced with the upgrade from the custom Pi Router to the ASUS RT-AX82U AX5400 Dual-Band WiFi 6 router. This change provides a robust foundation for the lab’s advanced computing and networking needs.

### Why the ASUS RT-AX82U AX5400?
The ASUS RT-AX82U AX5400 was selected for its superior performance and security features, which are essential for a high-demand lab environment:

- High Performance: The ASUS RT-AX82U supports WiFi 6, delivering faster speeds, reduced latency, and better performance, especially in environments with multiple connected devices.

- Advanced Security: With built-in AiProtection Pro, the router offers comprehensive protection against external threats, ensuring the security of sensitive operations like SSH tunneling.

- Optimized Latency and Bandwidth: The router’s advanced QoS features prioritize critical tasks, ensuring smooth and responsive performance for SSH connections and server operations.

## Current Network Architecture
- Hardlined Setup: The ASUS RT-AX82U is hardlined behind the primary household router, ensuring a secure and controlled network environment. All servers and devices are connected via a dedicated 5-port TP-Link unmanaged switch, providing stable and high-speed wired connections using CAT8 cables.

- Centralized Management: The ASUS RT-AX82U now manages all internal network traffic, with the switch handling the connections between the servers and the router. This setup minimizes latency and maximizes the efficiency of data transfers.

## Conclusion
The transition to the ASUS RT-AX82U AX5400 has solidified the home lab’s network infrastructure, offering the speed, security, and stability needed for advanced computing tasks. The hardlined configuration ensures reliable connectivity, making the lab a powerful and secure environment for ongoing projects and experiments.


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
