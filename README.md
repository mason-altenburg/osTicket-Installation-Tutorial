![image](https://github.com/user-attachments/assets/eef745f8-7011-47c5-aff3-4a3f05f59e70)

# osTicket-Installation-Tutorial
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

# osTicket - Prerequisites and Installation

## Environments and Technologies Used
- **Cloud Platform:** Microsoft Azure (Virtual Machines/Compute)
- **Remote Access:** Microsoft Remote Desktop (RDP)
- **Web Server:** Internet Information Services (IIS)
- **Operating System:** Windows 10
- **Tools:** Heidi SQL, osTicket Installation Files

## List of Prerequisites
- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

## Installation Steps

### Step 1: Create a Virtual Machine
Welcome to my first in-depth IT tutorial!  
1. Create a resource group named **"osTicket"** on [portal.azure.com](https://portal.azure.com).
2. Create a VM with 2-4 CPUs (this example uses 4 CPUs).
3. Connect to your VM via RDP using its public IPv4 address.  
*For Mac users, download Microsoft Remote Desktop (RDP).*

![Connecting to VM](images/rdp-connection.png)

### Step 2: Enable IIS
1. Access the Control Panel, select **"Turn Windows features on or off"**.
2. Enable **Internet Information Services (IIS)**.

![Enable IIS](images/enable-iis.png)

### Step 3: Install Web Platform Installer
1. Download and install the Web Platform Installer from [this link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

![Install Web Platform Installer](images/web-platform-installer.png)

### Step 4: Install Dependencies via Web Platform Installer
1. Install **MySQL 5.5**.
2. Install **x86 version of PHP** (up until 7.3).  
   - Note: Some files like the C++ redistributable package, PHP 7.3.8, and PHP Manager for IIS may show as failed and can be re-downloaded from the provided link.

...

*Continue with the rest of the tutorial content as provided...*

## Post-Installation Setup
- **Clean Up:** Delete `C:\inetpub\wwwroot\osTicket\setup` and set the permissions for `ost-config.php` to "Read" only.
- **Access Admin Panel:** Login to the osTicket Admin Panel at `http://localhost/osTicket/scp/login.php`.

---

Congratulations, if everything is installed correctly, osTicket should now be up and running on your Azure VM!

