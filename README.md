## DIOS Operating System
Design of an Intelligent Operating System for a Wireless Decentralized WAN

- [1. Summary](#1-summary)
- [2. Operating Principles under AI management](#2-operating-principles-under-ai-management)
- [3. Key Software Modules](#3-key-software-modules)
- [4. Resources](#4-resources)
- [5. How To Participate](#5-how-to-participate)
- [6. Conclusion](#6-conclusion)

---

### 1. Summary  

DIOS is envisioned as an innovative operating system coupled with an integrated software suite designed for a wireless, decentralized (P2P) WAN. It serves as the backbone for [DICS](https://github.com/FJortay/DICS-Collective-Management)—an intelligent, decentralized co-management platform for organizations ranging from local associations to state institutions that operate under the principles of direct democracy. Each DIOS node represents an individual member—a “citizen node”—and bundles all the necessary server and client software for:

- *Individual activities*:
  - *Front-end*:
    - Hosting the member’s ***website***;
    - Providing ***email*** and videoconferencing services;
    - Offering a ***commercial platform*** (disabled by default) for micro-enterprise management, which includes "Sales", "Accounting", and "Social Secretariat" modules linked to public service databases (taxation, social security, etc.).
  - *Back-end*:
    - Delivering decentralized DNS, identification, and authentication services.

- *Collective activities*:
  - *Front-end*:
    - Running the [DICS](https://github.com/FJortay/DICS-Collective-Management/) co-management system.
  - *Back-end*:
    - Coordinating a collective AI that distributes data storage and computational load across the network.

***Software and hardware context:***  
- *Software.* DIOS is built to be ***decentralized*** (modules are both client and server), ***modular*** (to ease technological evolution), and entirely composed of ***free software*** (as defined by [fsf.org](https://fsf.org)). 

- *Hardware.* Each organization member is expected to use two types of [free devices](https://www.gnu.org/philosophy/free-hardware-designs.html): a desktop computer and an IPV card (a yet-to-be-developed smart card-like device with a touchscreen and virtual keyboard, dedicated to identification, payments, and voting). Notably, the system avoids reliance on smartphones (due to concerns over mental health and computer security).

>***In P2P, OS is network***  
>In a P2P network, each node's operating system (OS) manages its local functions, and together, these OS instances form the entire network. In physical terms, it is accurate to consider that the OS installed on each node essentially represents the network as a whole.

In Sections 3, open source solutions are proposed for each component. Modules should be integrated in a standardized manner to streamline the system's evolvability (i.e., the replacement of existing modules with new ones). Indeed, many of these software packages were not originally developed with today’s conversational AI advances in mind. As such, significant parts of DICS may need to be built from scratch—or integrated with existing tools as a first step.


*DIOS Operating System, along with [DICS Collaborative Management](https://github.com/FJortay/DICS-Collaborative-Management), is part of the [DISCO Collective Intelligence](https://github.com/FJortay/DISCO-Collective-Intelligence) project.*

---

### **2. Operating Principles under AI management**

#### 2.1. Decentralized, Self-Organizing Architecture
  
- ***No Central Authority:*** All services (DNS, authentication, AI, etc.) are distributed among the nodes, ensuring that no single point of control exists.
  
- ***Auto-Organization and Self-Healing:*** The network dynamically incorporates new nodes, redistributes tasks, and manages failures autonomously, without centralized oversight.

#### 2.2. Collective Intelligence and Load Distribution
  
- ***Distributed AI:*** Nodes collaborate using federated learning and similar techniques to process data and perform computations, ensuring scalable and efficient resource utilization.
  
- ***Data Redundancy:*** Information is stored in a distributed fashion to enhance resilience, ensuring continuous service even if individual nodes go offline.

#### 2.3. Adaptation to Wireless WAN Constraints
  
- ***Dynamic Connectivity:*** The system is designed to manage multi-hop wireless communications and adapt to changing network conditions (e.g., node mobility, fluctuating bandwidth).
  
- ***Energy Efficiency:*** Optimized resource and power management allows operation on devices with limited power, ensuring sustained performance of low-power nodes.

#### 2.4. Security, Identity, and Privacy
  
- ***Robust Authentication:*** Each node possesses a self-sovereign identity secured via cryptographic protocols.
  
- ***End-to-End Security:*** All communications and transactions (including voting and payments) are encrypted and continuously monitored for threats.

#### 2.5. Modularity and Open Source Evolution
  
- ***Modular Design:*** The system is architected as independent, interoperable modules that can be updated or replaced as technology evolves.
  
- ***Free Software Commitment:*** Every module is developed and maintained as free/open source software, promoting transparency, collaboration, and adaptability.

---

### **3. Key Software Modules**

#### 3.1. Wireless Network Management and WAN Connectivity

- *Proposed Solutions:*  
  - ***[BATMAN-adv](https://www.open-mesh.org/projects/open-mesh/wiki):*** An open source mesh routing protocol enabling robust multi-hop wireless communication in dynamic environments.
   
- *Additional Option:*  
  - ***[OpenWrt](https://openwrt.org/):*** A Linux-based router firmware that optimizes wireless connectivity and manages network traffic on dedicated hardware.

#### 3.2. Decentralized DNS and Distributed Storage

- *Proposed Solution:*  
  - ***[IPFS/IPNS](https://ipfs.tech/):*** IPFS offers a distributed file system for data storage, while IPNS provides decentralized name resolution—together forming the backbone of a decentralized DNS.
    
- *Alternative:*  
  - ***[Namecoin](https://www.namecoin.org/):*** A blockchain-based open source solution for managing DNS records in a decentralized manner.

#### 3.3. Collective Intelligence (AI) and Load Distribution

- *Proposed Solution:*  
  - ***[TensorFlow Federated](https://www.tensorflow.org/federated):*** An open source framework for federated learning that supports decentralized training of AI models across nodes.
    
- *Alternative:*  
  - ***[PySyft](https://github.com/OpenMined/PySyft):*** A library for secure, privacy-preserving decentralized machine learning, facilitating distributed AI computation across nodes.

#### 3.4. Identification and Authentication
- *Proposed Solution:*  
  - ***[FreeIPA](https://www.freeipa.org/) / [OpenLDAP](https://www.openldap.org/):*** Open source identity management and authentication systems that can be configured for decentralized replication across nodes.

#### 3.5. Security and Cryptography

- *Secure Communication:*  
  - ***[WireGuard](https://www.wireguard.com/):*** A modern open source VPN providing efficient, secure, and encrypted communication between nodes.
   
- *Additional Tools:*  
  - ***[OpenSSL](https://www.openssl.org/)*** and ***[GnuPG](https://gnupg.org/):*** These libraries and utilities secure data exchanges, manage keys, and ensure data integrity.
    
- *Intrusion Detection:*  
  - ***[OSSEC](https://www.ossec.net/):*** An open source intrusion detection system (IDS) that monitors system and network activity to detect and respond to potential threats.

#### 3.6. Orchestration and Updates

- *Container Orchestration:*  
  - ***[Kubernetes](https://kubernetes.io/):*** (or ***[K3s](https://k3s.io/)*** for lightweight deployments) to manage and deploy DIOS services across nodes in a decentralized manner.
    
- *System Updates:*  
  - ***[OSTree](https://ostreedev.github.io/ostree/):*** An open source tool for managing bootable, versioned filesystem trees, enabling atomic and reliable system updates.
    
- *Configuration Automation:*  
  - ***[Ansible](https://www.ansible.com/)*** or ***[SaltStack](https://www.saltstack.com/):*** Tools to automate configuration management and deployment, ensuring consistency across the network.

#### 3.7. Energy

- *Energy Optimization:*  
  - ***[TLP](https://linrunner.de/tlp/):*** An open source Linux tool that optimizes power management and extends battery life on desktops and embedded devices.
    
- *Resource Monitoring:*  
  - ***[PowerTOP](https://github.com/fenrus75/powertop):*** A utility to monitor energy consumption and identify power-hungry processes, aiding in effective resource allocation.

---

### **4. Resources**

- **Theory:**  
  - [Wireless Ad Hoc Network – Wikipedia](https://en.wikipedia.org/wiki/Wireless_ad_hoc_network)
    
- **Free Software:**  
  - [GNUnet – Wikipedia](https://en.wikipedia.org/wiki/GNUnet)  
  - [FSF Directory](https://directory.fsf.org)
    
- **Free Hardware:**  
  - [FreedomBox](https://freedombox.org)  
  - [RYF – FSF](https://ryf.fsf.org)  
  - [H-Node](https://h-node.org)
       
---

### **5. How to Participate**

Help improve this first draft README. Once we agree on an elicitation plan, the *"Key Software Modules"* section will be split into several sub-projects. Your feedback and contributions are essential to evolve DIOS into a robust, AI-driven decentralized operating system.

---

### **6. Conclusion**

What once seemed unfeasible—building a comprehensive decentralized infrastructure like *"[DICS](https://github.com/FJortay/DICS-Collaborative-Management) on DIOS"* (composing [DISCO](https://github.com/FJortay/DISCO-Collective-Intelligence))—is now within reach. Advances in conversational AI empower us to design and implement collective intelligence systems with capabilities that were unimaginable just a few years ago. While the challenges remain significant, the potential benefits and insights from this research promise to be equally abundant and transformative.
