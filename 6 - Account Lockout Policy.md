# Setting Up a Lockout Policy

## Steps to Configure a Lockout Policy
1. Open **Group Policy Management** in the **Server Manager Dashboard**:
   - Navigate to **Tools** > **Group Policy Management**.

![image](https://github.com/user-attachments/assets/23db260a-2225-4173-8ed9-9d572a230cad)

2. Create a New GPO:
   - Right-click on the domain and select **Create a GPO in this domain and Link it here…**.
   - Add a name for your policy (e.g., `Account Lockout Policy`).

![image](https://github.com/user-attachments/assets/f4484ee4-853d-4d1b-a93a-f0b2a1b12299)

![image](https://github.com/user-attachments/assets/996be18c-7a85-433d-b9bf-ff7289b7d6c8)

3. Edit the GPO:
   - Right-click on the newly created policy and select **Edit**.

    ![image](https://github.com/user-attachments/assets/72fc6b0a-35e2-4419-8ec4-38b79aeec9e5)

   - Navigate to **Computer Configuration** > **Policies** > **Windows Settings** > **Security Settings** > **Account Policies** > **Account Lockout Policy** > **Account Lockout Threshold**.
   
   ![image](https://github.com/user-attachments/assets/6ac89f1f-a867-4521-8488-044ff507930e)

   - Check the box **Define this policy setting**.

    ![image](https://github.com/user-attachments/assets/1f31cb00-fedf-4ae7-a653-40f08cf905d6)

   - Set the number of invalid password attempts to `3` and click **Apply** and **OK**.
   - This ensures that a user’s account will be locked after three incorrect password entries.

5. Enforce the Policy:
   - Close the **Group Policy Management Editor** window.
   - In the **Group Policy Management** window, right-click on the policy and select **Enforced**.

  ![image](https://github.com/user-attachments/assets/110f290e-c4b3-4db5-ba26-240ea754d711)

## Testing the Lockout Policy
1. On a Windows domain machine, attempt to enter an invalid password three times for a user.

![image](https://github.com/user-attachments/assets/72c0ed7d-0d54-4d9e-8d8e-f4bde0d8e967)

## Unlocking the Account
1. In the **Windows Server domain controller**:
   - Open **Tools** > **Active Directory Users and Computers**.
   - Search for the locked-out user.

![image](https://github.com/user-attachments/assets/49b5e851-75d6-43bc-8c6f-51acf27f4f48)

2. Unlock the Account:
   - Right-click on the user’s name and select **Properties**.
   - Go to the **Account** tab to verify that their account is locked.

![image](https://github.com/user-attachments/assets/3848eab2-3181-4861-a5a2-92868a4ce2c5)

3. Reset the User’s Password:
   - Right-click on the user’s name again and select **Reset Password**.
   - Enter the new password and confirm the changes.

![image](https://github.com/user-attachments/assets/abc961ba-60b5-40eb-9837-28b7cb367079)

![image](https://github.com/user-attachments/assets/f11860d5-fbcb-4517-b441-ade2cd85136e)

![image](https://github.com/user-attachments/assets/6a7f9719-55b1-429b-85e4-faae73210ab7)
