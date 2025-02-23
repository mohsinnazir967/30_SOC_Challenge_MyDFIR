# Day 03: Setting Up an Elasticsearch Instance

## 1. Creating a Virtual Private Cloud (VPC)

- Sign up on **[Vultr](https://www.vultr.com/)** (use $300 credit if available).
- Navigate to **Products > Network > VPC 2.0**.
- Click **"Add VPC"** and configure:
    - **Location**: Ensure all VMs are in the same location (e.g., Singapore).
    - **IPv4 Range**: Set `172.31.0.0/20`.
    - **Name**: Example: `SOC_Simulation`.
    - Click **"Add Network"**.

## 2. Deploying the Virtual Machine (VM)

- Click **"Deploy"** > **"Deploy New Server"**.
- **Location**: Same as VPC (e.g., Singapore).
- **Image**: **Ubuntu** (64-bit).
- **Server Size**: **4 vCPUs, 16GB RAM**.
- **VPC Selection**: Choose the `SOC_Simulation`.
- **Hostname**: Example: `Challenge-ELK`.
- Click **"Deploy"** and wait until status is **Running**.

