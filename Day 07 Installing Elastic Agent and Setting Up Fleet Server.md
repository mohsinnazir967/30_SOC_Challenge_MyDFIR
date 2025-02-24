# Day 07: Installing Elastic Agent and Setting Up Fleet Server

## 1. Introduction

- **Goal**: Install Elastic Agent on Windows server and set up Fleet server for centralized management.
## 2. Create Fleet Server

- **Steps**:
    1. Click on **Deploy** > **Deploy New Server**.
    2. Select **Singapore** and **Ubuntu 22.04** (1 CPU, 4 GB RAM).
    3. Disable auto backups and IPv6.
    4. Select **Virtual Private Cloud.
    5. Ensure network is selected (IP: 172.31.0.4).
    6. Name the server `Challenge Fleet Server`.
    7. Click on **Deploy**.

## 3. Access Web GUI

- **Steps**:
    1. Go to public IP address on port 5601.
    2. Select the hamburger icon > **Fleet** under **Management**.
    3. Click on **Add Fleet Server**.
    4. Choose **Quick Start**.
    5. Name the server `my dfir Das Fleet DS server`.
    6. Enter the public IP (e.g., 155.138.1.155) with port 8220.
    7. Ensure URL is in HTTPS format.
    8. Click on **Generate Fleet Server Policy**.

## 4. Install Fleet Server

- **Steps**:
    1. Copy the generated token and configuration.
    2. Access the Fleet server via SSH.
    3. Update repositories: `apt-get update` and `apt-get upgrade -y`.
    4. Paste the copied configuration to install Elastic Agent.
    5. Ensure connection to Elasticsearch (port 9200).

## 5. Troubleshooting

- **Firewall Rules**:
    1. Modify firewall rules to allow Fleet server to access Elasticsearch.
    2. Use `ufw allow 9200` on the ELK server.
    3. Ensure Fleet server can communicate with ELK server.

## 6. Enroll Elastic Agent

- **Steps**:
    1. Confirm Fleet server connection.
    2. Click on **Continue Enrolling Elastic Agent**.
    3. Create a policy (e.g., `my defer D Windows d policy`).
    4. Select **Windows** as the host type.
    5. Copy the installation command.

## 7. Install Agent on Windows Server

- **Steps**:
    1. Access Windows server via console.
    2. Open PowerShell as Administrator.
    3. Paste and run the installation command.
    4. Ensure the agent downloads and installs successfully.

## 8. Additional Troubleshooting

- **Steps**:
    1. Check network connections and firewall settings.
    2. Allow port 8220 on the Fleet server: `ufw allow 8220`.
    3. Allow port 443 on the Fleet server: `ufw allow 443`.
    4. Modify Fleet server settings in the Elastic web GUI to use port 8220.
    5. Use `--insecure` flag to bypass self-signed certificate error.

## 9. Verify Enrollment

- **Steps**:
    1. Check the Elastic web GUI for the enrolled Windows server.
    2. Go to **Discover** and search for logs from the Windows server.
    3. Verify logs are being captured (e.g., event code 4625 for failed logon attempts).