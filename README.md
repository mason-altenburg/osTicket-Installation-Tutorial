![image](https://github.com/user-attachments/assets/eef745f8-7011-47c5-aff3-4a3f05f59e70)

---

## 🛠️ Environments & Technologies Used

- Microsoft Azure VM (Windows 10 Enterprise)
- Internet Information Services (IIS)
- MySQL Server 5.5
- PHP 7.3
- PHP Manager for IIS
- IIS URL Rewrite

---

## 📦 All Required Files  
Everything you need for this project is in the following Google Drive folder:  
🔗 [Download Everything Here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

---
Welcome to my first in-depth IT tutorial! To begin we will have to create a Virtual machine using the Microsoft Azure portal(portal.azure.com). We will be using a VM(virtual machine) which is a remote computer. We are using a VM in order to protect our physical machine just in case something malfunctions, and also have a clean slate computer to continually replicate the lab on. Create a resource group and title it "osTicket". Afterwards create a VM with 2-4 CPUs.
![Aure](https://github.com/user-attachments/assets/f7fb5401-2605-447d-89c4-d14ffc7fb8b8)
---
Next simply connect to your newly created VM using RDP using the public IPv4 address. If you are a Mac user you will have to download Microsoft Remote Desktop(RDP).  
![image](https://github.com/user-attachments/assets/100a3a47-5ebb-40eb-89e7-600853c579e8)

---

## Installation Steps

1️⃣ **Enable IIS**  
   - Control Panel → Programs → Turn Windows features on or off  
   - Check **Internet Information Services** → OK
   - ![enable-iis](https://github.com/user-attachments/assets/16d31fd3-8c99-44ef-8820-2a2711632863)



2️⃣ **Install Visual C++ Redistributable**  
   - Run `(https://aka.ms/vs/17/release/vc_redist.x86.exe)` → Accept license → Install → Finish

3️⃣ **Install & Configure MySQL 5.5**  
   - Run `mysql-5.5.62-win32.msi` → Typical → Next  
   - Configuration Wizard:  
     - Standard Configuration → Developer Machine  
     - Enable TCP/IP (port 3306)  
     - Install as Windows service → Start automatically  
     - Root password = **Password1** → Remove anonymous → Disallow remote root  
     - Execute → Finish  
   ![sql55 caputre](https://github.com/user-attachments/assets/e2fb84ae-4af0-4e5f-8761-b7724233b4ef)


4️⃣ **Install PHP 7.3**  
   - Extract `php-7.3.8-Win32-VC15-x86.zip` to `C:\php`  
   - Rename `php.ini-development` → `php.ini`  
   ![image](https://github.com/user-attachments/assets/105b70c1-ca92-4af4-8c0d-6a90e565cd14)


5️⃣ **Install PHP Manager for IIS**  
   - Run `PHPManagerForIIS.msi` → Next → Finish

6️⃣ **Install IIS URL Rewrite**  
   - Run `rewrite_amd64_*.exe` → Next → Finish

7️⃣ **Deploy osTicket**  
   - Extract osTicket ZIP → copy its **upload** folder to `C:\inetpub\wwwroot` → rename to **osTicket**  
  ![image](https://github.com/user-attachments/assets/25cea5a0-8990-4a98-a37e-acb15092c4fb)


8️⃣ **Configure IIS & PHP**  
   - IIS Manager → Default Web Site → osTicket → Browse → confirm installer loads  
   - PHP Manager → Enable `php_intl.dll` & `php_opcache.dll` → Refresh  
   ![osTicket setup page in browser](images/osticket-setup.png)

9️⃣ **Secure Config File**  
   - Rename `include\ost-sampleconfig.php` → `ost-config.php`  
   - Properties → Security → Disable inheritance → Remove all → Grant Everyone Read only

🔟 **Complete Installation**  
   - In browser click **Continue** → set Helpdesk name & default email  
   - Database = **osTicket**, Username = **root**, Password = **Password1** → Install Now!  
   - Delete `C:\inetpub\wwwroot\osTicket\setup`  
   - Set `include\ost-config.php` to Read‑only  
   - Login at http://localhost/osTicket/scp/login.php  
   ![osTicket installation success screen](images/osticket-success.png)

---

> **Note:** Only capture screenshots at the marked steps — everything else follows straightforward wizard clicks.


