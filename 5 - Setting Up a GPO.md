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
