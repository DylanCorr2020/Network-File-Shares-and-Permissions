<p align="center">
<img src="https://i.imgur.com/AeiqMDZ.png" alt="Traffic Examination"/>
</p>

# Network-File-Shares-and-Permissions

In this tutorial we will create some sample file shares with various permissions. 

## Prequisites 
Before starting this tutorial please check out the active directory lab as this will be a follow on from that. 


## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Domain Controller/Client Machine)
- Remote Desktop
- Shared Network Files

# Part One: Create Folders and Asign Permissions 

## Step 1: 

- Connect to DC-1 via remote desktop.
- Log in as admin "mydomain.com\jane_admin"

## Step 2: 

- Pick a random user in the _EMPLOYEES  in DC-1 directory and log into Client-1

## Step 3:

- On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”.

<img width="100%" hieght ="75%" alt="Image" src="https://github.com/user-attachments/assets/9a3de241-c9a7-4297-87f2-c6010640ecb3" />

## Step 4:

- Set the following permissions
- Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
- Right Click > read-access > properties > Sharing Tab > Click Share > Type     Domain Users > click Add > Give them read access > click Share button

<img width="100%" hieght ="75%" alt="Image" src="https://github.com/user-attachments/assets/1f6995a0-6896-42b8-845f-b22b184dcabb" />

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/7dddfa9a-351d-42cc-8d51-0eefa75acbe0" />

## Step 5:

- Repeat the steps above but for the other folders set the following permissions
- Folder: “write-access”,  Group: “Domain Users”,           Permissions: “Read/Write”

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/ede93af7-c2ae-47fe-a02e-4c232097d672" />

- Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/a7808cdc-a7c0-4845-8be0-6c2eb562d6d6" />


- (Skip accounting for now)


# Part Two: Test Access to Folders on Client-1

## Step 1:

- On Client-1, navigate to the shared folder (start, run, \\dc-1)
- Try to access the folders you just created. Which folders can you access?    Which folders can you create stuff in?

- If set up correctly you should not be able to open no-access folder get the following message

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/1122daac-d7d0-4b60-868d-eeca3608bee0" />

- <your user> is a part of the domain users group so we should be able to access the read-access but we not able to create files only read

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/4c799f70-9893-4c09-8cfc-9eec6f0c67d7" />

- Write access folder should allow you to create and save files 

- Accountants folder did not show because did not configure any sharing for it. 

  
# Part Three: Create an Accountants Security Group , assign permissions and test access


## Step 1:
- Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
- First create an Organizational Unit _GROUPS
- Right Click mydomian.com > new > Organisational Groups
- Once created right click on GROUPS > New > Group
- Name the group ACCOUNTANTS > click Okay


<img width="100%" height="75%"  alt="Image" src="https://github.com/user-attachments/assets/94460d31-3f78-45cc-8f3a-055f11a6dd27" />

## Step 2:


- On the “accounting” folder you created earlier, set the following permissions
- Folder "accounting" group "ACCOUNTANTS" Permissions: "Read/Write"

<img width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/8372b4d4-7ac1-4054-afc0-89ac02fe08ec" />


- On Client-1, as  <someuser>, try to access the accountants folder. It should fail.
- Log out of Client-1 as  <someuser>
- On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
- Go back into Active Directory Users and Computers > double click on ACCOUNTANTS security group > click members > click Add > add name of user > Click Check Names > click Okay
- Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?

  <img  width="100%" height="75%" alt="Image" src="https://github.com/user-attachments/assets/39801b59-6f72-4391-b795-7bcf0d202a7d" />








































  
