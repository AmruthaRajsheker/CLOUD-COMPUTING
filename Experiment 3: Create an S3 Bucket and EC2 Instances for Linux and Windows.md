## **Experiment 3: Create an S3 Bucket and EC2 Instances for Linux and Windows**



### **AIM:**
To create an S3 bucket and launch EC2 instances for both Linux and Windows on AWS.



### **EQUIPMENT REQUIRED:**

- AWS account.
- Internet access and a web browser.
- Permissions to create EC2 instances and S3 buckets in AWS.



### **THEORY:**

- **Amazon S3 (Simple Storage Service)** is a scalable object storage service used to store and retrieve any amount of data.
- **Amazon EC2 (Elastic Compute Cloud)** provides scalable compute capacity in the cloud, allowing you to launch virtual servers (instances) running various operating systems.



### **ALGORITHM / PROCEDURE:**

#### **1. Create an S3 Bucket:**

1. **Sign in to AWS Console:**
   - Sign in to the AWS Management Console using your IAM or root account.

2. **Navigate to S3:**
   - In the search bar, type "S3" and select **S3** under "Services".

3. **Create a New Bucket:**
   - Click on **Create bucket**.
   - Enter a **Bucket Name** (must be globally unique).
   - Choose an **AWS Region** (e.g., `us-east-1`).
   - Uncheck **Block all public access** if you need public access (optional).
   - Click **Create bucket**.

4. **Upload Files (Optional):**
   - After the bucket is created, select it and click on **Upload** to add files to the bucket.



#### **2. Create EC2 Instances (Linux and Windows):**

##### **A. Create a Linux EC2 Instance (e.g., Ubuntu):**

1. **Navigate to EC2:**
   - In the AWS Management Console, type "EC2" in the search bar and select **EC2**.

2. **Launch a New Instance:**
   - Click **Launch Instance**.
   - Select **Ubuntu Server** (or any other preferred Linux distribution) from the **Quick Start** tab.

3. **Choose Instance Type:**
   - Select the instance type (e.g., **t2.micro**) under the **Free Tier**.
   - Click **Next: Configure Instance Details**.

4. **Configure Instance:**
   - Configure instance settings (e.g., number of instances, network settings).
   - Click **Next: Add Storage** to set up the root volume size (default is usually 8GB).

5. **Configure Security Group:**
   - Add a security group with rules to allow **SSH (port 22)** access.
   - Click **Review and Launch**.

6. **Select Key Pair:**
   - Select **Create a new key pair** or choose an existing one.
   - Download the key pair file (**.pem**), which will be used to connect to the instance.

7. **Launch the Instance:**
   - Click **Launch** to create the Linux EC2 instance.

8. **Connect to the Linux Instance:**
   - Once the instance is running, select it and note the **Public IP**.
   - Use the following SSH command to connect to the instance:
     ```bash
     ssh -i /path/to/your-key.pem ubuntu@<Public-IP>
     ```



##### **B. Create a Windows EC2 Instance:**

1. **Navigate to EC2:**
   - In the AWS Management Console, go to **EC2**.

2. **Launch a New Instance:**
   - Click **Launch Instance**.
   - Select **Microsoft Windows Server** (e.g., **Windows Server 2019 Base**) from the **Quick Start** tab.

3. **Choose Instance Type:**
   - Select the instance type (e.g., **t2.micro**) under the **Free Tier**.
   - Click **Next: Configure Instance Details**.

4. **Configure Instance:**
   - Configure instance settings as needed (e.g., number of instances, network settings).
   - Click **Next: Add Storage** to configure storage (default is usually 30GB).

5. **Configure Security Group:**
   - Create a security group that allows **RDP (port 3389)** access.
   - Click **Review and Launch**.

6. **Select Key Pair:**
   - Select **Create a new key pair** or choose an existing one.
   - Download the key pair file (**.pem**), which will be used to decrypt the Windows Administrator password.

7. **Launch the Instance:**
   - Click **Launch** to create the Windows EC2 instance.

8. **Connect to the Windows Instance:**
   - Once the instance is running, select it and note the **Public IP**.
   - To get the **Administrator password**, click **Get Windows Password** (you will need to upload the **.pem** key).
   - Use **Remote Desktop Protocol (RDP)** to connect to the instance:
     - Open **Remote Desktop Connection** on your computer and enter the **Public IP** of the Windows instance.
     - Use the **Administrator password** to log in.



### **OUTPUTS:**

- **S3 Bucket**: A new S3 bucket is created successfully.
- **Linux EC2 Instance**: The Linux EC2 instance (e.g., Ubuntu) is launched and accessible via SSH.
- **Windows EC2 Instance**: The Windows EC2 instance is launched and accessible via RDP.



### **RESULT:**

The S3 bucket was created successfully, and both the Linux and Windows EC2 instances were launched and accessed without issues. The instances are now running and ready for further configuration or use.
