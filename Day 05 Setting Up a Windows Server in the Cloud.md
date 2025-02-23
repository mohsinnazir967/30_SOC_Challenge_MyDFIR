# Day 05 Setting Up a Windows Server in the Cloud

## 1. Deploying a Windows Server on Vultr

1. **Log in to Vultr**
    
    - Visit [**Vultr**](https://www.vultr.com/) and log in to your account.
        
2. **Deploy a New Server**
    
    - Click **Deploy** → **Deploy New Server**.
        
3. **Choose Server Type**
    
    - Select **Cloud Compute (Shared CPU)** (sufficient for this use case).
        
4. **Select a Location**
    
    - Choose a data center location (e.g., **Singapore**).
        
5. **Select an Operating System**
    
    - Choose **Windows Standard 2022 (latest version)**.
        
6. **Choose a Plan**
    
    - Select the cheapest option: **$24/month** (1 vCPU, 2GB RAM).
        
7. **Disable Additional Features**
    
    - **Auto backups** → Not required
        
    - **IPv6** → Not required
        
    - **Virtual Private Cloud (VPC)** → Not selected (for security reasons)
        
8. **Set Hostname
        
    - Example: `Cahllenge-win-haji`
        
9. **Deploy the Server**
    
    - Click **Deploy Now** and wait for the instance to start.

## 2. Accessing the Windows Server

**Check Server Status**

Wait until the server status changes to Running.

**Open the Console**

Click View Console.
 
If the server is still deploying, wait a few minutes.

**Log In to Windows Server**

Click the arrow button → Show Extra Keys → Send Ctrl+Alt+Del.

Copy and paste the password provided in Vultr.

Sign in to the Windows Server.


