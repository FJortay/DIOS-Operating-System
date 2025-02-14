# DIOS
Design of an Intelligent Operating System for a Wireless Decentralized WAN

## Plan
- [Summary](#summary)
- [Operating Principles](#operating-principles)
- [Key Software Modules](#key-software-modules)
- [Resources](#resources)
- [How To Participate](#how-to-participate)
- [Conclusion](#conclusion)

---

## Summary  

DIOS is envisioned as an intelligent operating system, with software suite, designed for a wireless, decentralized (P2P) WAN. DIOS is intended for organizations of all sizes — from local associations to states — operating under a co-governance model (direct democracy). Each DIOS node represents an individual member (a "citizen node") and includes all the server and client software required for:

- Hosting the member’s website ;
- Email, messaging, and videoconferencing services ;
- Decentralized DNS ;
- Identification and authentication ;
- Collective AI, which distributes data storage and computational load across the network ;
- Additional services as needed.

***Software and hardware context :*** 
- *Software* : the system should be modular (in order to allow for technological evolution) and composed entirely of free/open source software (as defined by [fsf.org](https://fsf.org)). Integration of existing solutions should be preferred to the development of new modules.
  
- *Hardware* : each organization member is assumed to use these two [free devices](https://www.gnu.org/philosophy/free-hardware-designs.html) : a desktop computer and an IPV card (a not yet existing smart card-like device with touchscreen and virtual keyboard, dedicated to identification, payments, and voting). The system should not rely on any use of the smartphone (for reasons of mental health and computer security).


*This is a "[Building AI course project](https://buildingai.elementsofai.com/)".*

---

## **Operating Principles**

1. **Decentralized, Self-Organizing Architecture**  
   - ***No Central Authority :*** all services (DNS, authentication, AI, etc.) are distributed among the nodes.
     
   - ***Auto-Organization and Self-Healing :*** the network dynamically integrates new nodes, redistributes tasks, and handles failures without centralized control.

2. **Collective Intelligence and Load Distribution**  
   - ***Distributed AI :*** nodes collaborate to process data and perform computations (using techniques such as federated learning), ensuring efficient resource utilization and scalability.
     
   - ***Data Redundancy :*** information is stored in a distributed manner, enhancing resilience and ensuring continuous service even if individual nodes fail.

3. **Security, Identity, and Privacy**  
   - ***Robust Authentication :*** each node has a self-sovereign identity secured by cryptographic protocols.
       
   - ***End-to-End Security :*** all communications and transactions (including voting and payments) are encrypted and continuously monitored for threats.

4. **Adaptation to Wireless WAN Constraints**  
   - ***Dynamic Connectivity :*** the system manages multi-hop wireless communications and adapts to changing network conditions (node mobility, varying bandwidth, etc.).
     
   - **Energy Efficiency :*** resource and power management is optimized to accommodate devices with limited power, ensuring sustained operation of low-power nodes.

5. **Modularity and Open Source Evolution**  
   - ***Modular Design :*** the system is divided into independent, interoperable modules that can be updated or replaced as technology advances.
      
   - ***Free Software Commitment :*** all modules are developed and maintained as free/open source software, ensuring transparency, collaboration, and flexibility.

---

## **Key Software Modules**

### **1. Wireless Network Management and WAN Connectivity Module**
- *Proposed Solutions :*  
  - ***BATMAN-adv :*** an open source mesh routing protocol that enables robust multi-hop wireless communication in dynamic environments.
- *Additional Option :*  
  - ***OpenWrt :*** a Linux-based firmware for routers that optimizes wireless connectivity and manages network traffic on dedicated hardware.

### **2. Decentralized DNS and Distributed Storage Module**
- *Proposed Solution :*  
  - ***IPFS/IPNS :*** IPFS provides a distributed file system for data storage, while IPNS offers decentralized name resolution—together forming the backbone of a decentralized DNS.
- *Alternative :*  
  - ***Namecoin :*** an open source blockchain-based solution for managing DNS records in a decentralized manner.

### **3. Identification,Authentication**
- *Proposed Solution :*  
  - ***FreeIPA / OpenLDAP :*** open source identity management and authentication systems that can be configured for decentralized replication across nodes.

### **4. Front-Office Services Module**
- *Web Hosting :*  
  - ***Apache HTTP Server*** or **Nginx**—both are robust open source web servers suitable for hosting member websites.
- *Email Services :*  
  - ***Postfix*** (MTA) combined with **Dovecot** (IMAP/POP3 server) to provide a secure and scalable email solution.
- *Videoconferencing:*  
  - ***Jitsi Meet :*** an open source videoconferencing platform ideal for decentralized communication services.

### **5. Collective Intelligence (AI) and Load Distribution Module**
- *Proposed Solution :*  
  - ***TensorFlow Federated :*** an open source framework for federated learning that enables decentralized training of AI models across multiple nodes.
- *Alternative :*  
  - ****PySyft :*** a library for secure and privacy-preserving decentralized machine learning, which supports distributed AI computation across nodes.

### **6. Security and Cryptography Module**
- *Secure Communication :*  
  - ***WireGuard :*** a modern open source VPN that provides efficient, secure, and encrypted communication between nodes.
- *Additional Tools :*  
  - ***OpenSSL*** and ***GnuPG :*** these tools provide cryptographic libraries and utilities for securing data exchanges, managing keys, and ensuring data integrity.
- *Intrusion Detection :*  
  - ***OSSEC :*** an open source intrusion detection system (IDS) that monitors system and network activity to detect and respond to potential threats.

### **7. Orchestration, Updates Management, and Governance Module**
- *Container Orchestration:*  
  - ***Kubernetes*** (or **K3s** for lightweight deployments) to manage and deploy DIOS services across nodes in a decentralized manner.
- *System Updates:*  
  - ***OSTree :*** an open source tool for managing bootable, versioned filesystem trees, enabling atomic and reliable system updates.
- *Configuration Automation:*  
  - ***Ansible*** or ***SaltStack :*** these tools facilitate automated configuration management and deployment across the network, ensuring consistency and ease of governance.

### **8. Energy and Resource Management Module**
- *Energy Optimization :*  
  - ***TLP :*** an open source tool for Linux that optimizes power management and extends battery life on desktop and embedded devices.
- *Resource Monitoring :*  
  - ***PowerTOP :*** a utility to monitor energy consumption and identify power-hungry processes, aiding in resource allocation and energy efficiency.

---

## **Resources**
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

## **How to participate**
Help improve this README. Once we agree on an elicitation plan, the *"Key Software Modules"* section will be split into several sub-projects.

---

## **Conclusion**

DIOS is a R&D project for an innovative, decentralized operating system for wireless WANs that supports collaborative governance, secure communications, and collective intelligence. By leveraging a modular architecture and integrating robust open source solutions—ranging from decentralized DNS and distributed storage to federated AI and secure identity management—DIOS could offer a scalable and flexible platform for organizations of all sizes. Its commitment to free software and modular design ensures that DIOS will evolve with technological advancements, maintaining transparency, security, and efficiency in a participatory and decentralized digital infrastructure.

In other words, DIOS is an infrastructure for collective intelligence and direct democracy.
