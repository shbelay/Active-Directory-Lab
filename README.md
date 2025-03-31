# Configuring Windows Server 2025 as a Domain Controller

## Change the Name of the Computer
1. Search for **View your PC name**.

![image](https://github.com/user-attachments/assets/8b12d403-f09a-4112-b22e-38b5d0a17fa1)

2. Click **Rename this PC** and rename the computer as `DC01` for Domain Controller 01.

![image](https://github.com/user-attachments/assets/752b195a-3872-45b8-ad17-c525ff6895db)

3. Click **Next** and restart the PC to apply the changes.

## Set Up the Server as a Domain Controller
1. In the **Server Manager** dashboard, go to **Manage** and click **Add Roles and Features**.

![image](https://github.com/user-attachments/assets/aacc6dcc-d188-4b82-82ad-01a159eebcec)

2. Follow these steps in the wizard:
   - **Before You Begin**: Click **Next**.
   - **Installation Type**: Select **Role-based or feature-based installation** and click **Next**.
   - **Server Selection**: Ensure the correct server is selected and click **Next**.
   - **Server Roles**: Check the box for **Active Directory Domain Services**, click **Add Features**, and click **Next**.
   - Click **Next** with the default selection for **Features** and **AD DS**.
   - In **Confirmation**, check the box to **Restart server automatically if required**, click **Yes**, and then click **Install**.

![image](https://github.com/user-attachments/assets/c388f2ae-9dfc-4fd7-8710-f97703e9309e)

3. When the installation is complete, click **Promote this server to a domain controller**.

![image](https://github.com/user-attachments/assets/44192ac7-db4f-44c8-a1ee-08477c3cd321)

4. In the new window:
   - Select **Add a new forest** and enter the domain name (e.g., `BelayAD-Lab.com`).
   - Click **Next**.

![image](https://github.com/user-attachments/assets/843839a5-032e-4c30-bd85-80489cad8ee6)

5. In **Domain Controller Options**:
   - Set the password (leave everything else as default).
   - Click **Next**.
6. Continue through the following:
   - **DNS Options**: Click **Next**.
   - **Additional Options**: Wait for the **NetBIOS domain name** to populate and click **Next**.
   - **Paths**: Leave the default settings and click **Next**.
   - **Review Options**: Click **Next**.
   - **Prerequisites Check**: Wait for the check to complete successfully and click **Install**.
7. The server will restart automatically upon completion.

![image](https://github.com/user-attachments/assets/30e15c7b-dbf9-4489-8b4b-d05dfbbb7857)

## Configure Active Directory Certificate Services
1. Once the server restarts:
   - Open the **Server Manager** dashboard.
   - Go to **Manage** and click **Add Roles and Features**.
2. In the wizard, click **Next** until you reach **Server Roles**.
3. Select **Active Directory Certificate Services**, click **Add Features**, and click **Next**.

![image](https://github.com/user-attachments/assets/09d38f34-bbbc-4385-b8ac-79ea21f708a5)

4. At the **Confirmation** step, check **Restart the destination server automatically if required** and click **Install**.

![image](https://github.com/user-attachments/assets/19fe439d-1374-4114-a549-06b8728b070b)

5. When installation completes, click **Configure Active Directory Certificate Services on the destination server**.

![image](https://github.com/user-attachments/assets/683396d9-a15b-4d56-88c5-21898f71103b)

6. In the **AD CS Configuration** wizard:
   - **Credentials**: Click **Next**.
   - **Role Services**: Select **Certification Authority**.
   - **Setup Type**: Choose **Standalone CA**.
   - **CA Type**: Select **Root CA**.
   - **Private Key**: Click **Next**.
   - **Cryptography**, **CA Name**, and **Validity Period**: Leave the default settings and click **Next**.
   - **Certificate Database**: Click **Next**.
   - **Confirmation**: Click **Configure**.
7. Close the wizard upon completion.
