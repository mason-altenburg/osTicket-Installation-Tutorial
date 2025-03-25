![image](https://github.com/user-attachments/assets/eef745f8-7011-47c5-aff3-4a3f05f59e70)

# osTicket – Prerequisites & Installation

This tutorial follows the original format, with screenshots only at key verification points.

---

## Environments & Technologies Used
- Microsoft Azure VM (Windows 10 Enterprise)
- Internet Information Services (IIS)
- MySQL Server 5.5
- PHP 7.3
- PHP Manager for IIS
- IIS URL Rewrite

---

## List of Prerequisites
- Visual C++ Redistributable (`VC_redist.x86.exe`)
- MySQL Server 5.5 (`mysql-5.5.62-win32.msi`)
- PHP 7.3 ZIP (`php-7.3.8-Win32-VC15-x86.zip`)
- PHP Manager for IIS (`PHPManagerForIIS.msi`)
- IIS URL Rewrite (`rewrite_amd64_*.exe`)
- osTicket v1.15.8 ZIP

---

## Installation Steps

1️⃣ **Enable IIS**  
   - Control Panel → Programs → Turn Windows features on or off  
   - Check **Internet Information Services** → OK  
   ![Windows Features with IIS enabled](images/enable-iis.png)

2️⃣ **Install Visual C++ Redistributable**  
   - Run `VC_redist.x86.exe` → Accept license → Install → Finish

3️⃣ **Install & Configure MySQL 5.5**  
   - Run `mysql-5.5.62-win32.msi` → Typical → Next  
   - Configuration Wizard:  
     - Standard Configuration → Developer Machine  
     - Enable TCP/IP (port 3306)  
     - Install as Windows service → Start automatically  
     - Root password = **Password1** → Remove anonymous → Disallow remote root  
     - Execute → Finish  
   ![MySQL Configuration Complete](images/mysql-config.png)

4️⃣ **Install PHP 7.3**  
   - Extract `php-7.3.8-Win32-VC15-x86.zip` to `C:\php`  
   - Rename `php.ini-development` → `php.ini`  
   ![C:\php folder contents](images/php-folder.png)

5️⃣ **Install PHP Manager for IIS**  
   - Run `PHPManagerForIIS.msi` → Next → Finish

6️⃣ **Install IIS URL Rewrite**  
   - Run `rewrite_amd64_*.exe` → Next → Finish

7️⃣ **Deploy osTicket**  
   - Extract osTicket ZIP → copy its **upload** folder to `C:\inetpub\wwwroot` → rename to **osTicket**  
   ![C:\inetpub\wwwroot\osTicket folder](images/osticket-folder.png)

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


