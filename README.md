# Table of Contents

- [1. Configuring Windows Server 2025 as a Domain Controller](#configuring-windows-server-2025-as-a-domain-controller)
- [2. Creating Domain Users](#creating-domain-users)
- [3. Attaching a Windows 11 Virtual Machine to a Domain](#attaching-a-windows-11-virtual-machine-to-a-domain)
- [4. Organizational Units and Groups](#organizational-units-and-groups)
- [5. Group Policy Objects](#setting-up-a-gpo-group-policy-object-to-set-a-wallpaper-for-the-it-support-department)


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

- [Back to the Top (Table of Contents)](#table-of-contents)
---

# Creating Domain Users

## Steps to Create and Organize Domain Users
1. Open **Server Manager** and navigate to **Tools** > **Active Directory Users and Computers**.

![image](https://github.com/user-attachments/assets/ad93dd7d-1a9e-4420-b0aa-c3599f29e387)

2. Expand the domain name by clicking the downward arrow, then select **Users**.

![image](https://github.com/user-attachments/assets/4f2ced54-c99e-4746-8bb8-db993ad9b616)

### Clean Up Security Groups
1. Windows Server includes built-in security groups. To organize them:
   - Right-click on the domain name.
   - Select **New** > **Organizational Unit**.
   - Enter a name for the Organizational Unit and click **OK**.

![image](https://github.com/user-attachments/assets/06292407-7a91-4fa7-b978-e39a1f57d7a2)

2. Return to **Users**, select all Security Groups, drag them to the newly created Organizational Unit, and click **Yes**.

![image](https://github.com/user-attachments/assets/ac609055-88cb-4fb8-9e6c-2ed49e5880d0)

### Create a New User
1. In the **Users** section, right-click in the white space and go to **New** > **User**.

![image](https://github.com/user-attachments/assets/9d4dbb63-4fb7-43a6-8199-90cad9660dca)

2. Fill in the user's name information and click **Next**.

![image](https://github.com/user-attachments/assets/628e045f-500a-4d16-ad08-b649a51b0365)

3. Enter the password information and follow the prompts to finish creating the user.

- [Back to the Top (Table of Contents)](#table-of-contents)
---

# Attaching a Windows 11 Virtual Machine to a Domain

## Add a New Network in VMware Workstation
1. Shut down the virtual machines.
2. Navigate to **Edit** > **Virtual Network Editor**.
3. Click **Change Settings** and confirm administrative changes by selecting **Yes**.

![image](https://github.com/user-attachments/assets/12326308-4b60-4e5e-b0b9-08ad27f2f82a)

4. Add a new network:
   - Click **Add Network** and select an available network.
   - Rename the network as desired and click **OK**.
   - Save the changes by clicking **OK**.

![image](https://github.com/user-attachments/assets/2b8eec88-fa8e-4268-8ebe-e616ca2cbbbb)

![image](https://github.com/user-attachments/assets/566343dd-9cb7-47ee-bdbf-0f666ce6a9ea)


## Configure Network for Virtual Machines
1. Open the settings for the virtual machines.
2. Under **Network Adapter**, select **Custom: Specific virtual network**.
3. From the drop-down menu, choose the newly created network.

![image](https://github.com/user-attachments/assets/cdba7f41-366c-4cbc-883a-c7b65d2deaaf)

## Configure the Domain Controller and Windows Machine
1. Start the Domain Controller server and the Windows machine.
2. Open **Command Prompt** and type `ipconfig` to view the IP configuration.

![image](https://github.com/user-attachments/assets/500e894a-df2e-436d-b30b-be5eb3e331bc)

3. On the Domain Controller machine:
   - Open **Control Panel** > **Network & Internet** > **Network and Sharing Center**.
   - Click **Change adapter settings** on the left pane.

![image](https://github.com/user-attachments/assets/5a2e9181-ca0f-4a28-972b-223e9000d51c)

   - Right-click the Ethernet adapter and select **Properties**.
   - Select **Internet Protocol Version 4 (TCP/IPv4)**, then click **Properties**.
 
   ![image](https://github.com/user-attachments/assets/ffaeafc0-1be8-4bb0-a858-6dc3f3921aa2)

   - Configure the following fields:
     - **IP Address**: Use the address shown in the `ipconfig` output.
     - **Subnet Mask**: Enter the appropriate mask.
     - **Default Gateway**: Match the one displayed earlier.
   - Click **OK** to apply the settings.

![image](https://github.com/user-attachments/assets/dd8e0cbf-b954-4aaf-80b0-2f65fb56a195)

4. Repeat these steps for the Windows machine but ensure:
   - The **Preferred DNS Server** is set to the IP address of the Domain Controller.

![image](https://github.com/user-attachments/assets/3a1df240-3311-436c-aada-ef504d68f562)

## Join the Windows Machine to the Domain
1. Rename the PC to your preference.
2. Assign the IP information to the Ethernet adapter as outlined above.
3. Search for **Access Work or School** and click **Connect**.

![image](https://github.com/user-attachments/assets/e54d0548-a599-4bc5-9e58-f175e963fb3e)

4. Select **Join this device to a local Active Directory domain**.

![image](https://github.com/user-attachments/assets/59b72586-7b3b-4b7d-b9d2-54795403a6f9)

5. Enter the domain name and user credentials (e.g., `pmiller` for the user logon name).

![image](https://github.com/user-attachments/assets/9ef006a6-a19e-4311-bd7d-aab2a4f5825b)

![image](https://github.com/user-attachments/assets/7391bd26-b294-494b-8e8d-7ab398469b76)

![image](https://github.com/user-attachments/assets/83204efa-afec-4139-8748-2bb6d28fb185)

6. Follow the prompts and restart the machine.

![image](https://github.com/user-attachments/assets/71be5c04-5002-4438-86c3-5e80b22a8624)


## Verify Domain Connection
1. After restarting, confirm that the Windows machine is connected to the domain.
2. On the Domain Controller:
   - Open **Active Directory Users and Computers**.
   - Verify the Windows machine appears under the **Computers** section.

![image](https://github.com/user-attachments/assets/2659c9b7-8dc3-4a20-b4f4-e11b65a7772c)

![image](https://github.com/user-attachments/assets/09ecf493-3113-4a80-89a0-c10c79cb08fd)

- [Back to the Top (Table of Contents)](#table-of-contents)
---

# Organizational Units and Groups

## Creating a New Organizational Unit
1. In the **Server Manager** dashboard, go to **Tools** > **Active Directory Users and Computers**.

![image](https://github.com/user-attachments/assets/bd56df7d-5ef9-43dd-bbb0-36979f5d5a81)

2. Right-click on the domain name, select **New** > **Organizational Unit**.
3. Enter the name for the OU. You can create various departments such as Engineering, Management, and IT. Using OUs can help you better manage users by allowing you to move or drag them into the appropriate unit.

![image](https://github.com/user-attachments/assets/a07a57d2-2bd7-4c4c-9082-ba3d7acd89d2)

> *Screenshot of Organizational Units*

![image](https://github.com/user-attachments/assets/dc0aa5a2-68b9-4eb5-a9f3-4b59d5698c12)

## Creating User Groups Within the OUs
1. Within each OU, create user groups as required. For example, in the Engineering OU, you might create a group called `EngineeringGroup`, while in the IT OU, you could create `ITManagement`, etc.

![image](https://github.com/user-attachments/assets/be7075fe-8c27-4359-829f-e2349dea1dbd)

2. Once the groups are created, either create new users or move existing users into the appropriate groups.
3. To add a specific user (e.g., Jarred Dunn) to the Engineering team:
   - Double-click on the desired group.
   - Click the **Members** tab.
   - Type the user’s name.
   - Click **Check Names**.
   - Click **Apply** and then **OK**.

![image](https://github.com/user-attachments/assets/3cbee7a2-3ff6-4e41-b698-2e990195f135)

# Creating a Shared Folder

## Setting Up the Shared Folder via Server Manager
1. Open **File and Storage Services** in **Server Manager**.

![image](https://github.com/user-attachments/assets/4bdfd5aa-3dd3-4a34-843f-60f4f6bfaaad)

2. Click on **Shares**.

![image](https://github.com/user-attachments/assets/cd39690b-1a2d-43a9-8c9b-20ca894cb328)

3. Click **Tasks** and then select **New Share**.

![image](https://github.com/user-attachments/assets/be67651a-78cc-4c8f-a3ef-6dee6ee27289)

### In the New Share Wizard:
1. **Profile**: Select `SMB Share - Quick` and click **Next**.
2. **Share Location**: Leave at the default setting and click **Next**.
3. **Share Name**: 
   - Enter your desired share name.
   - Take note of the "remote path to share" that is displayed.
   - Click **Next**.
4. **Other Settings**: Leave at the default selection and click **Next**.
5. **Permissions**:
   - Choose **Customize Permissions**.
   - Disable Inheritance and click **Convert inherited permissions into explicit permissions on this object**.
   - In the displayed window, adjust permissions by removing or adding users/groups as needed.
   - Click **OK** and then **Next**.
6. **Confirmation**: Click **Create** and then **Close** once the share is successfully created.

## Accessing the Shared Folder on a Windows 11 Machine
1. Log in to the Windows 11 machine.
2. Open **File Explorer**.
3. In the address bar, type the remote path to the share to access the folder.

![image](https://github.com/user-attachments/assets/69b85f7b-9c3e-4e64-8d74-be41a59f88d8)

![image](https://github.com/user-attachments/assets/2844343f-4fb9-41e3-af0c-80ab468d5990)

- [Back to the Top (Table of Contents)](#table-of-contents)
---

# Setting Up a GPO (Group Policy Object) to Set a Wallpaper for the IT Support Department

## Steps to Create the GPO:
1. Open **Group Policy Management** from the **Tools** menu.

![image](https://github.com/user-attachments/assets/7f1dd79d-c61d-49ef-814c-2ea0c50e0d4d)

2. Decide whether to apply the policy to the entire domain or a specific Organizational Unit (OU):
   - For this example, right-click on the **IT** OU and select **Create a GPO in this domain, and Link it here…**.

![image](https://github.com/user-attachments/assets/70af1859-9278-4e1f-8080-804a9dc6fc6f)

3. Enter a name for the GPO and click **OK**.

![image](https://github.com/user-attachments/assets/d2238776-acda-48b2-920f-49f02e774e3c)

## Editing the GPO:
1. Right-click on the newly created policy and select **Edit**.
2. In the policy editor, navigate to **Desktop Policy Settings**.
   - Policies that can be set are listed in this window.

### Setting the Desktop Wallpaper:
1. Locate the **Desktop Wallpaper** policy.
2. Double-click on **Desktop Wallpaper** to open its settings.

![image](https://github.com/user-attachments/assets/ba55ce4d-a70a-41e2-b96c-202031ed5c91)

3. Set the policy to **Enabled**.
4. Enter the path to the wallpaper file to be applied to the IT Support team desktops.
5. Save and exit the policy editor.

![image](https://github.com/user-attachments/assets/cf9e5f72-3239-4acb-8d5c-b3585dbd06d7)


- [Back to the Top (Table of Contents)](#table-of-contents)
---
