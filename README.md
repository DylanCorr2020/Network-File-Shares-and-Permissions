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

# Part One 

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


# Part Two 
















  
