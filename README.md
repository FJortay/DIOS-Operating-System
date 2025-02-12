# DIOS
Design of an Intelligent Operating System for a Wireless Decentralized WAN

## Plan
- [Summary](#summary)
- [Operating Principles](#operating-principles)
- [Key Software Modules](#key-software-modules)
- [How To Participate](#how-to-participate)
- [Conclusion](#conclusion)

---

## Summary  

DIOS is envisioned as an intelligent operating system, with software suite, designed for a wireless, decentralized WAN. DIOS is intended for organizations of all sizes — from local associations to states — that operate under a co-governance model (direct democracy). Each DIOS node represents an individual member (a "citizen node") and includes all the server and client software required for:

- Hosting the member’s website ;
- Email, messaging, and videoconferencing services ;
- Decentralized DNS ;
- Identification and authentication ;
- Collective AI, which distributes data storage and computational load across the network ;
- Additional services as needed.

The system is modular to allow for technological evolution and is composed entirely of free/open source software (as defined by fsf.org). Each organization member is assumed to use three [free devices](https://www.gnu.org/philosophy/free-hardware-designs.html) : a desktop computer  ; an IPV card (a bank card–like device with a touchscreen and virtual keyboard) dedicated to identification, payments, and voting ; a basic mobile phone (smartphones are intentionally excluded for health and security reasons : [learn more](https://jortay.net/theorie-liberation#neutraliser-addiction-ecrans)).


*This is a "Building AI course project".*

---

## **Operating Principles**

1. **Decentralized, Self-Organizing Architecture**  
   - **No Central Authority:** All services (DNS, authentication, AI, etc.) are distributed among the nodes.  
   - **Auto-Organization and Self-Healing:** The network dynamically integrates new nodes, redistributes tasks, and handles failures without centralized control.

2. **Collaborative Governance and Direct Democracy**  
   - **Co-management:** Every member (node) participates in decision-making, including system updates, resource allocation, and service management via secure electronic voting and payment systems.  
   - **Transparency and Accountability:** All operations and decisions are traceable and auditable, ensuring collective responsibility.

3. **Collective Intelligence and Load Distribution**  
   - **Distributed AI:** Nodes collaborate to process data and perform computations (using techniques such as federated learning), ensuring efficient resource utilization and scalability.  
   - **Data Redundancy:** Information is stored in a distributed manner, enhancing resilience and ensuring continuous service even if individual nodes fail.

4. **Security, Identity, and Privacy**  
   - **Robust Authentication:** Each node has a self-sovereign identity secured by cryptographic protocols.  
   - **End-to-End Security:** All communications and transactions (including voting and payments) are encrypted and continuously monitored for threats.

5. **Adaptation to Wireless WAN Constraints**  
   - **Dynamic Connectivity:** The system manages multi-hop wireless communications and adapts to changing network conditions (node mobility, varying bandwidth, etc.).  
   - **Energy Efficiency:** Resource and power management is optimized to accommodate devices with limited power, ensuring sustained operation of low-power nodes.

6. **Modularity and Open Source Evolution**  
   - **Modular Design:** The system is divided into independent, interoperable modules that can be updated or replaced as technology advances.  
   - **Free Software Commitment:** All modules are developed and maintained as free/open source software, ensuring transparency, collaboration, and flexibility.

---

## **Key Software Modules**

### **1. Wireless Network Management and WAN Connectivity Module**
- **Proposed Solution:**  
  - **BATMAN-adv:** An open source mesh routing protocol that enables robust multi-hop wireless communication in dynamic environments.
- **Additional Option:**  
  - **OpenWrt:** A Linux-based firmware for routers that optimizes wireless connectivity and manages network traffic on dedicated hardware.

### **2. Decentralized DNS and Distributed Storage Module**
- **Proposed Solution:**  
  - **IPFS/IPNS:** IPFS provides a distributed file system for data storage, while IPNS offers decentralized name resolution—together forming the backbone of a decentralized DNS.
- **Alternative:**  
  - **Namecoin:** An open source blockchain-based solution for managing DNS records in a decentralized manner.

### **3. Identification, Authentication, and Electronic Voting Module**
- **Proposed Solutions:**  
  - **FreeIPA / OpenLDAP:** Open source identity management and authentication systems that can be configured for decentralized replication across nodes.
  - **Helios Voting:** A free, open source electronic voting platform that ensures secure, verifiable, and transparent voting processes.

### **4. Front-Office Services Module**
- **Web Hosting:**  
  - **Apache HTTP Server** or **Nginx**—both are robust open source web servers suitable for hosting member websites.
- **Email Services:**  
  - **Postfix** (MTA) combined with **Dovecot** (IMAP/POP3 server) to provide a secure and scalable email solution.
- **Videoconferencing:**  
  - **Jitsi Meet:** An open source videoconferencing platform ideal for decentralized communication services.

### **5. Collective Intelligence (AI) and Load Distribution Module**
- **Proposed Solution:**  
  - **TensorFlow Federated:** An open source framework for federated learning that enables decentralized training of AI models across multiple nodes.
- **Alternative:**  
  - **PySyft:** A library for secure and privacy-preserving decentralized machine learning, which supports distributed AI computation across nodes.

### **6. Security and Cryptography Module**
- **Secure Communication:**  
  - **WireGuard:** A modern open source VPN that provides efficient, secure, and encrypted communication between nodes.
- **Additional Tools:**  
  - **OpenSSL** and **GnuPG:** These tools provide cryptographic libraries and utilities for securing data exchanges, managing keys, and ensuring data integrity.
- **Intrusion Detection:**  
  - **OSSEC:** An open source intrusion detection system (IDS) that monitors system and network activity to detect and respond to potential threats.

### **7. Orchestration, Updates Management, and Governance Module**
- **Container Orchestration:**  
  - **Kubernetes** (or **K3s** for lightweight deployments) to manage and deploy DIOS services across nodes in a decentralized manner.
- **System Updates:**  
  - **OSTree:** An open source tool for managing bootable, versioned filesystem trees, enabling atomic and reliable system updates.
- **Configuration Automation:**  
  - **Ansible** or **SaltStack:** These tools facilitate automated configuration management and deployment across the network, ensuring consistency and ease of governance.

### **8. Energy and Resource Management Module**
- **Energy Optimization:**  
  - **TLP:** An open source tool for Linux that optimizes power management and extends battery life on desktop and embedded devices.
- **Resource Monitoring:**  
  - **PowerTOP:** A utility to monitor energy consumption and identify power-hungry processes, aiding in resource allocation and energy efficiency.

---

## **How to participate**
Help improve *"Operating principle"* and *"Key software modules"* sections. Once we agree on this elicitation plan, we will split the *"Key Software Modules"* section into several sub-projects.

---

## **Conclusion**

DIOS is a project for an innovative, decentralized operating system for wireless WANs that supports collaborative governance, secure communications, and collective intelligence. By leveraging a modular architecture and integrating robust open source solutions—ranging from decentralized DNS and distributed storage to federated AI and secure identity management—DIOS could offer a scalable and flexible platform for organizations of all sizes. Its commitment to free software and modular design ensures that DIOS will evolve with technological advancements, maintaining transparency, security, and efficiency in a participatory and decentralized digital infrastructure.

In other words, DIOS is an infrastructure for collective intelligence and direct democracy.
