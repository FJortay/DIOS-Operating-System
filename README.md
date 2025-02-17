# DIOS
Design of an Intelligent Operating System for a Wireless Decentralized WAN

- [1. Summary](#1-summary)
- [2. Operating Principles under AI management](#2-operating-principles-under-ai-management)
- [3. Key Software Modules](#3-key-software-modules)
- [4. Resources](#4-resources)
- [5. How To Participate](#5-how-to-participate)
- [6. Conclusion](#6-conclusion)

---

### 1. Summary  

DIOS is envisioned as an intelligent operating system, with software suite, designed for a wireless, decentralized (P2P) WAN. DIOS is intended to be the infrastructure of [DICS](https://github.com/FJortay/DICS), an intelligent and decentralised co-management web platform for organizations of all sizes (local associations, companies, municipalities, State) willing to operate under the rules of direct democracy. Each DIOS node represents an individual member (a "citizen node") and includes all the server and client software required for:

   - *Individual activities* :
      - *Front-end* :
         - hosting the member’s ***website***;
         - ***email*** and videoconferencing services;
         - a ***commercial platform*** (disabled by default) : intended for individuals willing to manage a micro-enterprise ; composed of "Sales", "Accounting" and "Social Secretariat" modules, all linked to the public service database (taxation, social security,...).
      - *Back-end* : ***decentralized*** DNS, Identification and authentication.
     
   - *Collective activities* :
      - *Front-end* : [DICS](https://github.com/FJortay/DICS/)  co-management system;
      - *Back-end* : collective AI, with distributed data storage and computational load across the network.


***Software and hardware context :*** 
- *Software.* The system should be ***decentralized*** (therefore both client and server), ***modular*** (in order to facilitate technological evolution) and exclusively composed of ***free software*** (as defined by [fsf.org](https://fsf.org)). 
  
- *Hardware* : each organization member is assumed to use two kinds of [free devices](https://www.gnu.org/philosophy/free-hardware-designs.html) : a desktop computer and an IPV card (a not yet existing smart card-like device with touchscreen and virtual keyboard, dedicated to identification, payments, and voting). The system should not rely on any use of smartphone (for reasons of mental health and computer security).

>***HI + AI = CI.*** Nodes are the network. They are the agents of plasticity (learning) and emergence (nodes interactions and diversity). Humans may provide creativity, ethical judgment, or complex decision-making, while AI offers speed, pattern recognition, and data processing. The emergent collective intelligence is the product of this collaboration.

In sections 3, an open source solution is mentioned for each point. However, these software were not designed and developed in the current new era of conversational AI. As a result, much of DIOS may need to be built from scratch.  Nevertheless, assessing what is presently available may be a good choice for a first step. And the second one may even consist in integrating them... 

*This is a "[Building AI course project](https://buildingai.elementsofai.com/)".*

---

### **2. Operating Principles under AI management**

#### 2.1. Decentralized, Self-Organizing Architecture
  
   - ***No Central Authority :*** all services (DNS, authentication, AI, etc.) are distributed among the nodes.
     
   - ***Auto-Organization and Self-Healing :*** the network dynamically integrates new nodes, redistributes tasks, and handles failures without centralized control.

#### 2.2. Collective Intelligence and Load Distribution  
   - ***Distributed AI :*** nodes collaborate to process data and perform computations (using techniques such as federated learning), ensuring efficient resource utilization and scalability.
     
   - ***Data Redundancy :*** information is stored in a distributed manner, enhancing resilience and ensuring continuous service even if individual nodes fail.

#### 2.3. Adaptation to Wireless WAN Constraints  
   - ***Dynamic Connectivity :*** the system manages multi-hop wireless communications and adapts to changing network conditions (node mobility, varying bandwidth, etc.).
     
   - ***Energy Efficiency :*** resource and power management is optimized to accommodate devices with limited power, ensuring sustained operation of low-power nodes.

#### 2.4. Security, Identity, and Privacy  
   - ***Robust Authentication :*** each node has a self-sovereign identity secured by cryptographic protocols.
       
   - ***End-to-End Security :*** all communications and transactions (including voting and payments) are encrypted and continuously monitored for threats.

#### 2.5. Modularity and Open Source Evolution

   - ***Modular Design :*** the system is divided into independent, interoperable modules that can be updated or replaced as technology advances.
      
   - ***Free Software Commitment :*** all modules are developed and maintained as free/open source software, ensuring transparency, collaboration, and flexibility.

---

### **3. Key Software Modules**

#### 3.1. Wireless Network Management and WAN Connectivity
- *Proposed Solutions :*  
  - ***[BATMAN-adv](https://www.open-mesh.org/projects/open-mesh/wiki) :*** an open source mesh routing protocol that enables robust multi-hop wireless communication in dynamic environments.
- *Additional Option :*  
  - ***[OpenWrt](https://openwrt.org/) :*** a Linux-based firmware for routers that optimizes wireless connectivity and manages network traffic on dedicated hardware.

#### 3.2. Decentralized DNS and Distributed Storage
- *Proposed Solution :*  
  - ***[IPFS/IPNS](https://ipfs.tech/) :*** IPFS provides a distributed file system for data storage, while IPNS offers decentralized name resolution—together forming the backbone of a decentralized DNS.
- *Alternative :*  
  - ***[Namecoin](https://www.namecoin.org/) :*** an open source blockchain-based solution for managing DNS records in a decentralized manner.

#### 3.3. Collective Intelligence (AI) and Load Distribution
- *Proposed Solution :*  
  - ***[TensorFlow Federated](https://www.tensorflow.org/federated) :*** an open source framework for federated learning that enables decentralized training of AI models across multiple nodes.
- *Alternative :*  
  - ***[PySyft](https://github.com/OpenMined/PySyft) :*** a library for secure and privacy-preserving decentralized machine learning, which supports distributed AI computation across nodes.

#### 3.4. Identification and Authentication
- *Proposed Solution :*  
  - ***[FreeIPA](https://www.freeipa.org/) / [OpenLDAP](https://www.openldap.org/) :*** open source identity management and authentication systems that can be configured for decentralized replication across nodes.

#### 3.5. Security and Cryptography
- *Secure Communication :*  
  - ***[WireGuard](https://www.wireguard.com/) :*** a modern open source VPN that provides efficient, secure, and encrypted communication between nodes.
- *Additional Tools :*  
  - ***[OpenSSL](https://www.openssl.org/)*** and ***[GnuPG](https://gnupg.org/) :*** these tools provide cryptographic libraries and utilities for securing data exchanges, managing keys, and ensuring data integrity.
- *Intrusion Detection :*  
  - ***[OSSEC](https://www.ossec.net/) :*** an open source intrusion detection system (IDS) that monitors system and network activity to detect and respond to potential threats.

#### 3.6. Orchestration and Updates
- *Container Orchestration:*  
  - ***[Kubernetes](https://kubernetes.io/)*** (or ***[K3s](https://k3s.io/)*** for lightweight deployments) to manage and deploy DIOS services across nodes in a decentralized manner.
- *System Updates:*  
  - ***[OSTree](https://ostreedev.github.io/ostree/) :*** an open source tool for managing bootable, versioned filesystem trees, enabling atomic and reliable system updates.
- *Configuration Automation:*  
  - ***[Ansible](https://www.ansible.com/)*** or ***[SaltStack](https://www.saltstack.com/) :*** these tools facilitate automated configuration management and deployment across the network, ensuring consistency and ease of governance.

#### 3.7. Energy
- *Energy Optimization :*  
  - ***[TLP](https://linrunner.de/tlp/) :*** an open source tool for Linux that optimizes power management and extends battery life on desktop and embedded devices.
- *Resource Monitoring :*  
  - ***[PowerTOP](https://github.com/fenrus75/powertop) :*** a utility to monitor energy consumption and identify power-hungry processes, aiding in resource allocation and energy efficiency.
---

## **4. Resources**
- Theory
   - [wikipedia.org/Wireless_ad_hoc_network](https://en.wikipedia.org/wiki/Wireless_ad_hoc_network)
- Free software
   - [wikipedia.org/GNUnet](https://en.wikipedia.org/wiki/GNUnet)
   - [directory.fsf.org](https://directory.fsf.org)

- Free hardware
   - [freedombox.org](https://freedombox.org)
   - [ryf.fsf.org](https://ryf.fsf.org)
   - [h-node.org](https://h-node.org)
       
---

## **5. How to participate**
Help improve this first draft README. Once we agree on an elicitation plan, the *"Key Software Modules"* section will be split into several sub-projects.

---

## **6. Conclusion**

Before 2023, a project like the [DICS](https://github.com/FJortay/DICS)/DIOS system would have seemed unfeasible for a long time to come. But since then, conversational AI has emerged. It will not only help us design this collective intelligence system but also grant it capabilities that were unimaginable just a few years ago. The challenges to overcome, or circumvent, are certainly numerous and high, but in any case, the fruits of this research will be just as numerous and enriching.
