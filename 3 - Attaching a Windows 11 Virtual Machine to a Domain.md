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
