# On-premises Active Directory Deployed in the Cloud (Azure)
![image-file](https://github.com/Muzeyenshemsi/User-Creation-in-Active-Directory/assets/171860463/adeb35e3-5e02-4002-bb88-0c2fda970665)


## Introduction

Creating user accounts in an on-premises Active Directory (AD) deployed in the cloud using Microsoft Azure is a crucial task for managing your organization's IT infrastructure. Azure provides a flexible and scalable platform for hosting AD, enabling efficient user and resource management. Proper user account creation ensures that employees have the necessary access to resources and systems while maintaining security and compliance standards.

In this guide, we will walk you through the step-by-step process of creating a new user account in an on-premises Active Directory deployed in Azure. We will cover the prerequisites, detailed instructions, best practices, and additional resources to help you effectively manage user accounts in your organization.


### Environments and Technologies Used
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

### Operating Systems Used
- Windows Server (Domain Controller)
- Windows 10 

## Prerequisites

Before you begin, ensure you have the following prerequisites:

1. **Azure Subscription**:Ensure you have an active Azure subscription to deploy and manage your virtual machines and network resources.

2. **Active Directory Deployment**: Ensure that on-premises Active Directory is properly deployed and configured on a virtual machine within your Azure environment. This includes having a domain controller set up and accessible.

3. **Administrative Privileges**: You must have the necessary administrative privileges to create and manage user accounts in Active Directory.

4. **Access to Active Directory Users and Computers (ADUC) Console**: Ensure that you have access to the ADUC console on the Azure-hosted domain controller.

5. **Organizational Unit (OU)**: Determine the Organizational Unit (OU) where the new user account will be created. OUs help in organizing user accounts and applying group policies.

6. **User Information**: Gather the necessary information for the new user account, including:
   - Username
   - Full name
   - Password (ensure it meets the organization's password policy requirements)
   - Additional user details (e.g., email address, phone number)

Having these prerequisites in place will ensure a smooth and efficient user creation process in an on-premises Active Directory deployed within Azure Virtual Machines.

## High-Level Deployment and Configuration Steps

### 1. Deploy Azure Virtual Machines
- **Create Virtual Machines**:
   - Create your Domain Controller using VM (Windows Server 2022)
   - Create Windows 10 VM for your user account
- **Provision Virtual Machines**: Make sure all your Virtual Machines are in the same Virtual Network
      
### 2. Configure Active Directory on Azure VM
- **Install Active Directory Domain Services (AD DS)**: Use the Server Manager on your Windows Server VM to install the AD DS role.
- **Promote the Server to a Domain Controller**: Run the AD DS Configuration Wizard to promote the server to a domain controller and create a new AD forest.

### 3. Configure Networking
- **Set Up DNS**: Configure DNS settings to ensure proper name resolution within your AD domain.
- **Establish Connectivity**: Ensure that your VMs can communicate within the VNet and with external resources if needed.

### 4. Manage Active Directory
- **Create OUs**: Organize your directory structure by creating Organizational Units (OUs) for users, computers, and other objects.
- **Create User Accounts**: Use the ADUC console to create and manage user accounts within your AD domain.

## Demonstration

### Step-by-Step Instructions

1. **Launch Active Directory Users and Computers (ADUC) Console**
   - Open the ADUC console on your Azure-hosted domain controller. This can typically be done by running `dsa.msc` from the Run dialog (Win + R).

2. **Navigate to the OU (Organizational Unit)**
   - In the ADUC console, navigate to the Organizational Unit (OU) where you want to create the new user account. OUs are used to organize and manage users, groups, and computers.

3. **Create New User**
   - Right-click on the desired OU, select `New`, and then `User`.
   - Enter the following details for the new user:
     - **First Name**: Enter the user's first name.
     - **Last Name**: Enter the user's last name.
     - **User Logon Name**: Enter a unique username for the user.

   ![Create New User](https://github.com/Muzeyenshemsi/User-Creation-in-Active-Directory/assets/171860463/88e08a12-6dc2-43e9-b374-ec7c3fca50b6)


4. **Set User Password**
   - Enter and confirm a password for the user. Ensure the password meets your organization's policy requirements.
   - Configure account options such as `User must change password at next logon` or `Password never expires` based on your requirements.

![Set User Password](https://github.com/Muzeyenshemsi/User-Creation-in-Active-Directory/assets/171860463/02b0bb89-7337-49f9-9a3e-52f2d10b3fec)


5. **Complete User Creation**
   - Review the details and click `Finish` to create the user account.
   - Verify that the new user account appears in the selected OU.

6. **Assign User to Groups (Optional)**
   - To assign the user to specific groups, right-click on the user account, select `Properties`, and navigate to the `Member Of` tab.
   - Add the user to the necessary groups to grant appropriate permissions and access rights.

![Assing User to Group](https://github.com/Muzeyenshemsi/User-Creation-in-Active-Directory/assets/171860463/fb4ee72e-2413-4db7-8efd-f0a5adbda780)



### Best Practices

- **Naming Conventions**: Follow consistent naming conventions for user accounts to ensure clarity and uniformity.
- **Password Policies**: Implement strong password policies to enhance security.
- **Group Memberships**: Assign users to groups based on their roles and responsibilities to streamline permission management.

## Additional Resources

- [Microsoft Docs: Active Directory Users and Computers](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/ad-ds-administrative-tools)
- [Azure Documentation: Deploy a Windows Server VM](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)

## Conclusion

Creating user accounts in an on-premises Active Directory deployed in Azure is an essential task for IT administrators. By following the steps outlined in this guide and adhering to best practices, you can ensure efficient and secure user management within your organization.

---
