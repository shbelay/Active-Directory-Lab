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
