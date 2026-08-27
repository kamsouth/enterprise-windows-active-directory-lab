
# Enterprise Windows & Active Directory Home Lab

## Overview

This lab simulates a small enterprise Windows environment using Windows Server and Active Directory. The environment was built to practice domain administration, identity management, DNS, Group Policy, PowerShell automation, and troubleshooting.

## Technologies

- Windows Server
- Active Directory Domain Services
- DNS
- Group Policy
- PowerShell
- Windows client systems
- VirtualBox

## Lab Architecture

- DC01 - Windows Server Domain Controller
- Windows domain-joined workstation
- Active Directory users and groups
- Organizational Units
- Group Policy Objects
- Internal DNS

## What I Configured

- Installed and configured Active Directory Domain Services
- Created a Windows domain
- Created users, groups, and organizational units
- Joined Windows endpoints to the domain
- Configured Group Policy
- Configured DNS
- Used PowerShell for account and group administration
- Troubleshot authentication and connectivity issues

## Skills Demonstrated

- Windows Server administration
- Active Directory administration
- DNS troubleshooting
- Group Policy management
- PowerShell
- Identity and access management
- Enterprise infrastructure troubleshooting

## Steps and Screenshots

## Step 1 - Configured the Windows Server Host

Configured the Windows Server host as DC01 and verified its domain membership, network configuration, and server status before using it as the domain controller for the lab.
<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/5511c0c3-db6c-49a7-9d26-049fe048ca53" />


## Step 2 - Configure Static IP and DNS

Configured a static IPv4 address and DNS settings on DC01 to provide consistent network addressing for Active Directory services.

The domain controller was configured to use the internal DNS environment so domain-joined systems could reliably locate Active Directory services.
<img width="1301" height="959" alt="16_Windows_Server_Static_IPv4_and_DNS_Configuration" src="https://github.com/user-attachments/assets/60761454-0258-4ce5-a063-0a307a41d4cb" />




## Step 3 - Configured Active Directory Domain Services 

Installed Active Directory Domain Services and configured DC01 as the domain controller, providing centralized authentication and management for users, groups, and computers.
<img width="1918" height="957" alt="image" src="https://github.com/user-attachments/assets/c271e3cf-fceb-4acc-b518-60750fcc8011" />








## Step 4 - Configured DNS

Configured and reviewed DNS on DC01 to provide internal name resolution and support Active Directory domain discovery and authentication.
<img width="1915" height="951" alt="image" src="https://github.com/user-attachments/assets/a70e9841-286f-43a7-b3c9-7d9638001b57" />



## Step 5 - Reviewed DNS 
I also reviewed the forward lookup zone and DNS host records to verify that systems within the domain could be resolved by hostname.
<img width="1301" height="1001" alt="06_DNS_Manager_Forward_Lookup_Zone_and_Host_Record" src="https://github.com/user-attachments/assets/bdc19e81-0f05-4707-8e35-8b3fd24e9330" />



## Step 6 - Create Active Directory Organizational Units

Created Organizational Units in Active Directory to logically separate and manage users, computers, and other domain resources.

Using OUs also allowed Group Policy settings to be applied to specific groups of systems instead of applying every policy across the entire domain.

<img width="1301" height="999" alt="04_Active_Directory_Organizational_Unit_Creation" src="https://github.com/user-attachments/assets/f74a1eba-4c12-48a2-96a6-d00deb59d5b7" />


## Step 7 - Created a Workstation Security GPO

Created a custom Workstation Security Policy Group Policy Object and configured password-related security settings to demonstrate centralized policy management within the Windows domain.

<img width="1915" height="948" alt="image" src="https://github.com/user-attachments/assets/5060a47c-a30a-4ace-87ec-dbdaab751ad4" />






## Step 8 - Linked the GPO to the Workstations OU

Linked the Workstation Security Policy to the Workstations Organizational Unit so the configured security settings can be centrally applied to domain-joined workstation systems.
<img width="1912" height="943" alt="image" src="https://github.com/user-attachments/assets/fc0bb563-0671-43e8-ac2d-0a9987c71e82" />








## Step 9 - Used PowerShell for Active Directory Administration

Used PowerShell to query and validate Active Directory domain information, review user accounts, and inspect security groups within the lab environment.
<img width="1916" height="968" alt="image" src="https://github.com/user-attachments/assets/a5c3f2db-ce60-4a67-aec5-9f8ac99a0406" />


<img width="1918" height="379" alt="image" src="https://github.com/user-attachments/assets/1f3ec777-26ef-4585-95c3-741c8935a0c8" />


<img width="1916" height="1005" alt="image" src="https://github.com/user-attachments/assets/7323f77e-7cfc-463e-ab52-eaf5870e1273" />


Commands Used:

Get-ADDomain

Get-ADUser -Filter * | Select-Object Name, Enabled

Get-ADGroup -Filter * | Select-Object Name


## Step 10 - Validate DNS and Domain Connectivity

Used PowerShell and Windows networking tools to validate DNS resolution and communication between systems in the lab environment.

I confirmed that the client system could resolve DC01 by hostname and communicate with the domain controller, helping verify that the internal DNS and Active Directory network configuration were functioning correctly.

<img width="1301" height="1057" alt="11_SIEM01_DNS_Configuration_and_DC01_Name_Resolution" src="https://github.com/user-attachments/assets/d92a997d-aba4-49d0-86b0-e762c86fb2b4" />









