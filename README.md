# DIOS Operating System  
Design of an Intelligent Operating System for a Wireless Decentralized WAN

- [Summary](#summary)
- [1. Operating Principles under AI management](#1-operating-principles-under-ai-management)
- [2. Key Software Modules](#2-key-software-modules)
- [3. Resources](#3-resources)
- [4. Project Phases](#4-project-phases)
- [5. How To Participate](#5-how-to-participate)
- [6. Conclusion](#6-conclusion)

---

## Summary

DIOS is (a project for) an innovative operating system paired with an integrated software suite tailored for a wireless, decentralized (P2P) WAN. It serves as the backbone for [DICS](https://github.com/FJortay/DICS-Collaborating-System) platform—a smart, decentralized co-management system designed for organizations ranging from local associations to state institutions practicing direct democracy. Each DIOS node represents an individual “citizen node” and bundles both server and client functionalities for:

- *Individual activities:*
  - *Front-end:*
    - Hosting a personal ***website***;
    - Providing ***email*** and videoconferencing services;
  - *Back-end:*
    - Delivering decentralized DNS, identification, and authentication services.

- *Collective activities:*
  - *Front-end:*
    - Running the [DICS](https://github.com/FJortay/DICS-Collaborating-System/) collaborating system.
  - *Back-end:*
    - Orchestrating a collective AI that distributes data storage and computational tasks across the network.

***Software and hardware context:***  
- *Software.* DIOS is engineered to be ***decentralized*** (each module acts as both client and server), ***modular*** (to facilitate technological evolution), and entirely composed of ***free software*** (as defined by [fsf.org](https://fsf.org)). 

- *Hardware.* Each organization member is expected to use two types of [free devices](https://www.gnu.org/philosophy/free-hardware-designs.en.html): a desktop computer and an IPV card—a forthcoming smart card-like device featuring a touchscreen and virtual keyboard dedicated to identification, payments, and voting. Notably, the system deliberately avoids the use of smartphones, addressing concerns regarding mental health and cybersecurity.

>***In P2P, OS is network***  
>Within a P2P network, each node’s operating system manages local functions; collectively, these OS instances represent the entire network.

In Section 3, open source solutions are proposed for each component. Modules must be integrated in a standardized fashion to ensure the system remains adaptable and evolvable. Since many existing packages were not originally conceived with today’s conversational AI in mind, significant portions of DIOS might need to be newly developed or adapted from current tools.

*DIOS Operating System, together with [DICS Collaborating System](https://github.com/FJortay/DICS-Collaborating-System), is an integral part of the [DISCO Collective Intelligence](https://github.com/FJortay/DISCO-Collective-Intelligence) project.*

---

## 1. Operating Principles under AI management

### 1.1. Decentralized, Self-Organizing Architecture
  
- ***No Central Authority:***  
  All services—from DNS and authentication to AI processing—are distributed among nodes, eliminating any single point of control.
  
- ***Auto-Organization and Self-Healing:***  
  The network dynamically incorporates new nodes, redistributes tasks, and autonomously manages failures.

### 1.2. Collective Intelligence and Load Distribution
  
- ***Distributed AI:***  
  Nodes collaborate through federated learning and related techniques, ensuring scalable data processing and efficient resource utilization.
  
- ***Data Redundancy:***  
  Information is stored in a distributed manner, bolstering resilience and ensuring continuous operation even if individual nodes fail.

### 1.3. Adaptation to Wireless WAN Constraints
  
- ***Dynamic Connectivity:***  
  The system is designed to handle multi-hop wireless communications, adapting in real time to fluctuating network conditions.
  
- ***Energy Efficiency:***  
  Optimized resource and power management enables sustained performance on devices with limited energy supplies.

### 1.4. Security, Identity, and Privacy
  
- ***Robust Authentication:***  
  Each node is assigned a self-sovereign identity, safeguarded through advanced cryptographic protocols.
  
- ***End-to-End Security:***  
  All communications and transactions—including voting and payments—are encrypted and continuously monitored for potential threats.

### 1.5. Modularity and Open Source Evolution
  
- ***Modular Design:***  
  The architecture consists of independent, interoperable modules that can be updated or replaced as technology advances.
  
- ***Free Software Commitment:***  
  Every component is developed as open source, ensuring transparency, collaboration, and long-term adaptability.

---

## 2. Key Software Modules

### 2.1. Wireless Network Management and WAN Connectivity

- *Proposed Solutions:*  
  - ***[BATMAN-adv](https://www.open-mesh.org/projects/open-mesh/wiki):***  
    An open source mesh routing protocol that ensures robust multi-hop wireless communication in dynamic environments.
   
- *Alternative Option:*  
  - ***[OpenWrt](https://openwrt.org/):***  
    A Linux-based router firmware that optimizes wireless connectivity and manages network traffic on dedicated hardware.

### 2.2. Decentralized DNS and Distributed Storage

- *Proposed Solution:*  
  - ***[IPFS/IPNS](https://ipfs.tech/):***  
    IPFS offers a distributed file system for data storage while IPNS provides decentralized name resolution, together forming the backbone of a decentralized DNS.
    
- *Alternative:*  
  - ***[Namecoin](https://www.namecoin.org/):***  
    A blockchain-based solution for managing DNS records in a decentralized framework.

### 2.3. Collective Intelligence (AI) and Load Distribution

- *Proposed Solution:*  
  - ***[TensorFlow Federated](https://www.tensorflow.org/federated):***  
    An open source framework for federated learning that supports decentralized training of AI models across nodes.
    
- *Alternative:*  
  - ***[PySyft](https://github.com/OpenMined/PySyft):***  
    A library facilitating secure, privacy-preserving decentralized machine learning.

### 2.4. Identification and Authentication

- *Proposed Solution:*  
  - ***[FreeIPA](https://www.freeipa.org/) / [OpenLDAP](https://www.openldap.org/):***  
    Open source identity management systems that can be configured for decentralized replication across nodes.

### 2.5. Security and Cryptography

- *Secure Communication:*  
  - ***[WireGuard](https://www.wireguard.com/):***  
    A modern VPN solution offering efficient, secure, and encrypted communications between nodes.
   
- *Additional Tools:*  
  - ***[OpenSSL](https://www.openssl.org/)*** and ***[GnuPG](https://gnupg.org/):***  
    These utilities secure data exchanges, manage cryptographic keys, and ensure data integrity.
    
- *Intrusion Detection:*  
  - ***[OSSEC](https://www.ossec.net/):***  
    An open source intrusion detection system that monitors system and network activity to identify potential threats.

### 2.6. Orchestration and Updates

- *Container Orchestration:*  
  - ***[Kubernetes](https://kubernetes.io/):***  
    (or ***[K3s](https://k3s.io/)*** for lightweight deployments) to manage and deploy DIOS services in a decentralized fashion.
    
- *System Updates:*  
  - ***[OSTree](https://ostreedev.github.io/ostree/):***  
    Manages bootable, versioned filesystem trees, ensuring atomic and reliable system updates.
    
- *Configuration Automation:*  
  - ***[Ansible](https://www.ansible.com/)*** or ***[SaltStack](https://www.saltstack.com/):***  
    Automate configuration management and deployment for consistent network-wide settings.

### 2.7. Energy

- *Energy Optimization:*  
  - ***[TLP](https://linrunner.de/tlp/):***  
    An open source tool that optimizes power management, extending battery life on desktops and embedded devices.
    
- *Resource Monitoring:*  
  - ***[PowerTOP](https://github.com/fenrus75/powertop):***  
    Monitors energy consumption to identify power-hungry processes and improve resource allocation.

---

## 3. Resources

### Theory:  
  - [Wireless Ad Hoc Network – Wikipedia](https://en.wikipedia.org/wiki/Wireless_ad_hoc_network)
    
### Free Software:  
  - [GNUnet – Wikipedia](https://en.wikipedia.org/wiki/GNUnet)  
  - [FSF Directory](https://directory.fsf.org)
    
### Free Hardware: 
  - [FreedomBox](https://freedombox.org)  
  - [RYF – FSF](https://ryf.fsf.org)  
  - [H-Node](https://h-node.org)
       
---

## 4. Project Phases

1. Improve this README (deadline: t+1Y).

2. Test the functioning of basic front-office applications (website and email) on a P2P LAN, using existing free software (deadline: t+3Y).

3. Based on the information collected during the previous phase:
   
   - Detail missing features;
     
   - Define standards for systemic scalability of DIOS modular components (deadline: t+4Y).

4. Develop the missing back-office applications for the functioning of basic front-office applications on a P2P WAN (deadline: t+6Y).

5. Integrate [DICS Collaborating System](https://github.com/FJortay/DICS-Collaborating-System) on DIOS (deadline: t+8Y).

---

## 5. How To Participate

We are at phase 1. Help improve this README.

---

## 6. Conclusion

What once seemed unfeasible—building an all-encompassing decentralized infrastructure such as "[DICS](https://github.com/FJortay/DICS-Collaborating-System) on DIOS" (forming the basis of [DISCO](https://github.com/FJortay/DISCO-Collective-Intelligence))—is now within reach. Advances in conversational AI empower us to design and implement collective intelligence systems with unprecedented capabilities. Although significant challenges remain, the potential rewards in innovation, security, and democratic engagement are immense and transformative.
