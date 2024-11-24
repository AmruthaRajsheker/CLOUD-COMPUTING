## **Experiment 4: Setting Up a Scalable File Storage System Using Amazon Elastic File System (EFS)**



### **AIM:**
To set up a scalable file storage system using Amazon Elastic File System (EFS) for storing and managing files in the cloud.



### **EQUIPMENT REQUIRED:**

1. **Hardware:**
   - A computer with internet access.

2. **Software:**
   - Web browser (e.g., Chrome, Firefox).
   - AWS account with permissions to create EFS and EC2 instances.

3. **Tools:**
   - AWS Management Console.



### **THEORY:**

**Amazon Elastic File System (EFS)** is a fully managed, scalable file storage service that can be mounted on multiple EC2 instances at once. EFS supports standard file protocols (NFS) and is suitable for a wide variety of use cases, including content management, big data analytics, and web server clusters. It is elastic and automatically scales as you add or remove data.



### **ALGORITHM / PROCEDURE:**

#### **1. Create an Amazon Elastic File System (EFS):**

1. **Sign in to AWS Management Console:**
   - Log in to your AWS account via the [AWS Management Console](https://aws.amazon.com/console/).

2. **Navigate to Amazon EFS:**
   - In the search bar, type **EFS** and select **Amazon EFS** from the services list.

3. **Create a New EFS File System:**
   - Click **Create file system**.
   - Choose a **VPC** (e.g., `default VPC` or a custom one if applicable).
   - Select the **Availability Zone** for your file system (or leave it set to default for multi-availability zone support).
   - For **Performance Mode**, select **General Purpose** (or Max I/O for higher throughput applications).
   - For **Throughput Mode**, select **Bursting** or **Provisioned** depending on your requirements.
   - Click **Next** to configure additional settings.

4. **Configure EFS Access Points (Optional):**
   - You can create access points for applications to securely access specific directories in EFS. For this basic experiment, leave this option unchecked.

5. **Review and Create:**
   - Review your configuration and click **Create File System**. 
   - Once the file system is created, note the **DNS name** of the EFS.



#### **2. Mount EFS on an EC2 Instance:**

1. **Launch an EC2 Instance:**
   - In the AWS Management Console, navigate to **EC2** and click **Launch Instance**.
   - Choose an **Amazon Linux** or **Ubuntu** instance type (e.g., **t2.micro** for free tier eligibility).
   - In the **Configure Instance** step, choose the **VPC** and **Subnet** matching the EFS file system.
   - For **Security Group**, ensure that you allow inbound **NFS (port 2049)** traffic.
   - Launch the instance and download the key pair for SSH access.

2. **SSH into EC2 Instance:**
   - Once the EC2 instance is running, obtain its **Public IP** from the EC2 dashboard.
   - SSH into the instance using the downloaded key:
     ```bash
     ssh -i /path/to/your-key.pem ec2-user@<EC2-Public-IP>
     ```

3. **Install NFS Client:**
   - Run the following command to install the NFS client on your EC2 instance:
     ```bash
     sudo yum install -y nfs-utils    # For Amazon Linux
     sudo apt-get install nfs-common  # For Ubuntu
     ```

4. **Create a Mount Point:**
   - Create a directory on your EC2 instance where you will mount the EFS:
     ```bash
     sudo mkdir /mnt/efs
     ```

5. **Mount the EFS File System:**
   - Run the following command to mount the EFS file system:
     ```bash
     sudo mount -t nfs -o nfsvers=4.1 <EFS-DNS-NAME>:/ /mnt/efs
     ```
   - Replace `<EFS-DNS-NAME>` with the DNS name of your EFS file system (e.g., `fs-xxxxxx.efs.us-east-1.amazonaws.com`).

6. **Verify the Mount:**
   - Run the following command to verify that the EFS file system is successfully mounted:
     ```bash
     df -h /mnt/efs
     ```



#### **3. Test the EFS File Storage:**

1. **Create Files on EFS:**
   - Inside the mounted directory `/mnt/efs`, create some test files to check the functionality:
     ```bash
     echo "Hello EFS!" > /mnt/efs/testfile.txt
     ```

2. **Verify the Files:**
   - List the files in the mounted directory:
     ```bash
     ls /mnt/efs
     ```
   - You should see the `testfile.txt` file that you created.

3. **Access EFS from Another EC2 Instance (Optional):**
   - Launch another EC2 instance in the same VPC.
   - Repeat steps 2-5 from the "Mount EFS on an EC2 Instance" section on this new instance.
   - You should be able to see and access the files created from the first EC2 instance.



### **OUTPUTS:**

- A scalable Amazon EFS file system is created and mounted on EC2 instances.
- Test files are created and accessed from multiple EC2 instances.



### **RESULT:**

The Amazon EFS file system was successfully set up, and the EC2 instance was able to mount it. Files created in the EFS were accessible across multiple EC2 instances, confirming the scalability and shared access of the storage system.
