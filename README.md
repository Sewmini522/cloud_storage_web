# ☁️ Azure Blob Storage File Uploader - Complete Guide

A complete hands-on project for uploading files to Azure Blob Storage through a web interface, using an Azure Virtual Machine as the web server.


## 📋 Project Overview

This project demonstrates a complete cloud application development workflow:
1. **Create Azure Virtual Machine** (Ubuntu 24.04 LTS)
2. **Host a web page** on the VM using Apache2
3. **Create Azure Storage Account** with Blob Storage
4. **Build a file upload interface** with HTML/CSS/JavaScript
5. **Connect to Blob Storage** using SAS tokens
6. **Upload files directly** from browser to Azure


## 🎯 Features

- ✅ Complete step-by-step Azure setup guide
- ✅ Virtual Machine configuration with SSH access
- ✅ Apache2 web server setup on Ubuntu
- ✅ Storage Account and Container creation
- ✅ CORS configuration for secure browser uploads
- ✅ SAS token generation for temporary access
- ✅ Drag-and-drop file upload interface
- ✅ Real-time upload progress tracking
- ✅ Success confirmation page
- ✅ Direct browser-to-blob storage uploads


## 🛠️ Technologies Used

| Category               | Technologies                               |
|------------------------|--------------------------------------------|
| **Cloud Platform**     | Microsoft Azure                            |
| **Compute**            | Azure Virtual Machines (Ubuntu 24.04 LTS)  |
| **Storage**            | Azure Blob Storage                         |
| **Web Server**         | Apache2                                    |
| **Frontend**           | HTML5, CSS3, JavaScript (ES6)              |
| **Azure SDK**          | Azure Storage Blob SDK v12                 |
| **Authentication**     | SAS (Shared Access Signatures) Tokens      |
| **SSH Client**         | PuTTY / PuTTYgen                           |


**📋Steps - Azure Blob Storage Uploader**

Part 1: Create VM on Azure

1.Login to Azure Portal
2.Go to Virtual Machines → + Create → Virtual Machine
3.Fill: Name: my-vm / Image: Ubuntu 24.04 LTS / Size: Free tier / Username: azureuser / SSH public key (generate with PuTTYgen)
4.Disk: Standard HDD
5.Networking: Keep defaults
6.Click Review + create → Create

Part 2: Connect to VM

1.Copy VM's Public IP
2.Open PuTTY → Paste IP
3.Go to: Connection → SSH → Auth → Browse (select private key)
4.Click Open
5.Login: azureuser

Part 3: Setup Web Server

sudo apt-get update
sudo apt-get install apache2 -y

Part 4: Open HTTP Port in Azure

1.Stop VM
2.Go to Networking → Add port 80 (HTTP)
3.Start VM

Part 5: Create Storage Account

1.Go to Storage accounts → + Create
2.Name: blobstorage123 (unique)
3.Region: Same as VM
4.Click Review + create → Create

Part 6: Create Container

1.Open Storage Account → Containers → + Container
2.Name: uploads
3.Click Create

Part 7: Configure CORS

1.Storage Account → Resource sharing (CORS)
2.Add rule:Allowed origins: *
           Allowed methods: GET, PUT, POST, DELETE, HEAD
           Allowed headers: *
           Exposed headers: *
3.Click Save

Part 8: Generate SAS Token

1.Container uploads → Generate SAS
2.Permissions: ✓ Read ✓ Write ✓ Create ✓ List
3.Click Generate SAS token and URL
4.Copy the SAS URL

Part 9: Create Web Page on VM

cd /var/www/html
sudo nano index.html

Part 10: Test!

1.Open browser: http://<YOUR_VM_PUBLIC_IP>
2.Drag & drop files
3.Click Upload


🎯 How It Works
User Uploads File → JavaScript picks file → Azure Blob SDK called
        ↓
SAS Token authenticates request → File uploaded directly to Blob Storage
        ↓
Progress tracked in real-time → Success page displayed → File appears in container

##ScreenShots

![image](https://github.com/user/repo/assets/xxxx)<img width="1433" height="661" alt="Picture63" src="https://github.com/user-attachments/assets/e13b26e2-75d9-4b13-852f-721a7eb075e6" />

![image](https://github.com/user/repo/assets/xxxx)<img width="1681" height="844" alt="Picture64" src="https://github.com/user-attachments/assets/ce6f918f-683a-460e-a70c-a0190e53064a" />

![image](https://github.com/user/repo/assets/xxxx)<img width="1866" height="875" alt="Picture66" src="https://github.com/user-attachments/assets/ccbf6ccb-d57f-414a-82dd-09bbb35bfa61" />

![image](https://github.com/user/repo/assets/xxxx)<img width="1918" height="882" alt="Picture67" src="https://github.com/user-attachments/assets/82ce66bc-d3c5-4be4-9881-637df2ba8bc1" />

