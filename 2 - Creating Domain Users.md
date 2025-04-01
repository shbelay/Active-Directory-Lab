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
