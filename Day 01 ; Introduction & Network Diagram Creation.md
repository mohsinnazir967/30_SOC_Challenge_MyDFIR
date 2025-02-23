# Day 01 ; Introduction & Network Diagram Creation

## Introduction

- The 30-day challenge aims to help aspiring SOC analysts gain practical experience.
- Created by Steven, a cybersecurity professional with 8 years of experience in security operations.
- Focuses on hands-on skills to build confidence.

### Network Diagram Using Draw.io

1. Accessing Draw.io
    
    - Open [draw.io](https://www.draw.io).
    - Explore basic tools: Shapes (General Tab), Grid, Background, Styles.

2. Creating the Network Diagram
    
    - Cloud Provider: Vultr (Hosting all virtual machines).
    - Servers & Computers in the Setup:
        - Elastic & Kibana Server
        - Windows Server (RDP enabled)
        - Ubuntu Server (SSH enabled)
        - Fleet Server
        - OS Ticket Server
        - C2 (Command & Control) Server (Marked in Red)
        - SOC Analyst Laptop 
        - Attacker Laptop (Marked in Red)

3. Configuring the Virtual Private Cloud (VPC)
    
    - VPC (Virtual Private Cloud) groups all servers in a private network.
    - Subnet Range: `172.31.0.0/24`
        - IP Range: `172.31.0.1 – 172.31.0.254`
        - Subnet Mask: `255.255.255.0`

4. Connecting Components
    
    - Windows & Ubuntu Servers → Fleet Server (Managed Agents)
    - Fleet Server → Elastic & Kibana (Data Forwarding)
    - OS Ticket Server ↔ Elastic & Kibana (Alerts & Tickets)
    - Windows & Ubuntu Servers → Elastic & Kibana (Log Forwarding)
    - Internet Gateway & Internet Cloud → Provide internet access.
    - SOC Analyst Laptop → Elastic & Kibana (Web GUI)
    - Attacker Laptop (Marked in Red) → C2 Server (Mythic)

5. Finalizing the Diagram
    
    - Used different colors & line styles to represent connections.
    - Ensured bidirectional arrows where applicable.
    - Labeled all connections & functionalities.