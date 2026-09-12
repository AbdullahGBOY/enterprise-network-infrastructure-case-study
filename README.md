# Enterprise Network Infrastructure Case Study

## Project Overview

Design and implementation of a resilient enterprise network infrastructure serving multiple industrial buildings, factories, administrative departments, production areas, security systems, and operational services.

The infrastructure supports approximately 370 users, 125 IP surveillance cameras, 33 network switches, and 18 distributed network racks.

The project was initiated in 2025 and continues through ongoing monitoring, maintenance, and infrastructure improvement.

## My Role

As IT Manager, I was responsible for:

- Designing the overall network architecture
- Planning network segmentation and connectivity
- Supervising the implementation
- Coordinating with the specialized implementation company
- Reviewing infrastructure requirements
- Planning network resilience and service continuity
- Managing the ongoing development of the infrastructure

The project was completed in cooperation with Lina Amer, Assistant IT Department Supervisor, and a specialized external implementation company.

## Infrastructure Scale

| Component | Scale |
|---|---:|
| Supported users | Approximately 370 |
| IP surveillance cameras | 125 |
| Network switches | 33 |
| Network racks | 18 |
| Facilities | Multiple factories and buildings |
| Internet providers | Two independent providers |

## Internet Connectivity and Redundancy

The internet infrastructure uses two independent connections:

- Local internet service provider
- Starlink satellite internet connection

MikroTik is used to manage load balancing and automatic failover between both connections. If the primary service becomes unavailable, internet traffic is automatically transferred to the secondary connection to maintain operational continuity.

## Network Segmentation

The infrastructure is divided into multiple VLANs based on operational requirements:

- Administration
- Production
- CCTV and surveillance
- Guest access
- Servers
- Biometric attendance systems
- PBX and telephony

This segmentation improves network organization, performance, security, and control between different business systems.

## Security Architecture

A Fortinet firewall provides centralized network protection and traffic control.

The security design supports:

- Network segmentation
- Controlled communication between business services
- Internet traffic protection
- Separation of guest and internal networks
- Protection of servers and operational systems
- Continuous monitoring and policy management

Specific firewall rules, internal addressing, and security configurations are intentionally excluded from this public case study.

## Fiber-Optic Infrastructure

The distributed network racks and facilities are interconnected using fiber-optic links.

A fiber-ring architecture provides path redundancy across the site. If a fiber connection is interrupted, network traffic can be redirected through the available path to reduce service interruption and maintain connectivity across the affected area.

Each infrastructure location is supported by a UPS system to provide temporary power continuity for network equipment.

## Wireless Infrastructure

The wireless infrastructure uses Ruijie access points managed through Ruijie Cloud.

Coverage was expanded by installing additional access points in areas suffering from weak or inconsistent wireless connectivity.

The wireless environment supports internal users while maintaining separation between corporate and guest access.

## CCTV Infrastructure

The surveillance infrastructure includes approximately 125 Hikvision IP cameras connected to NVR recording systems.

Each camera is documented and assigned a dedicated internal IP address. This improved camera identification, monitoring, troubleshooting, and management across the different facilities.

CCTV traffic is separated from other operational services through a dedicated network segment.

## Challenges

Before the infrastructure improvements, the environment experienced:

- Weak wireless coverage in several areas
- Difficulty identifying and tracking individual cameras
- Service interruption when the primary internet provider failed
- Risk of network interruption caused by fiber-link failure
- Increased complexity across multiple buildings and factories
- A need for stronger separation between operational systems

## Implemented Solutions

- Increased the number of wireless access points
- Introduced centralized Ruijie Cloud management
- Documented cameras and assigned dedicated internal addresses
- Implemented dual-provider load balancing and automatic failover
- Segmented the network through dedicated VLANs
- Deployed Fortinet firewall protection
- Connected infrastructure through fiber-optic links
- Implemented a resilient fiber-ring architecture
- Provided UPS protection for distributed network equipment
- Organized connectivity through 18 racks and 33 switches

## Results

The implementation delivered:

- Improved wireless coverage across the facilities
- Greater internet service continuity
- Automatic transition between internet providers
- Stronger isolation between business systems
- Improved camera identification and troubleshooting
- Better resilience against fiber-link interruption
- Centralized wireless network visibility
- A scalable foundation for future expansion
- Improved management of users, production systems, CCTV, servers, and telephony

## Technologies

- MikroTik
- Fortinet
- Ruijie Cloud
- Ruijie Access Points
- Cisco Networking
- Hikvision IP Cameras
- Network Video Recorders
- Fiber-Optic Infrastructure
- VLAN Segmentation
- Dual-WAN Load Balancing
- Automatic Internet Failover
- UPS Power Protection

## Simplified Architecture

```mermaid
flowchart TB
    ISP1[Local Internet Provider]
    ISP2[Starlink]

    ISP1 --> MT[MikroTik Load Balancing and Failover]
    ISP2 --> MT
    MT --> FW[Fortinet Firewall]
    FW --> CORE[Core Network]
    CORE --> RING[Fiber-Optic Ring]
    RING --> RACKS[18 Distributed Network Racks]

    RACKS --> ADMIN[Administration VLAN]
    RACKS --> PROD[Production VLAN]
    RACKS --> CCTV[CCTV VLAN]
    RACKS --> GUEST[Guest VLAN]
    RACKS --> SERVERS[Servers VLAN]
    RACKS --> BIOMETRIC[Biometric Systems VLAN]
    RACKS --> PBX[PBX and Telephony VLAN]
