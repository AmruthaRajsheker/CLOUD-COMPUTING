## **Experiment 5: Relational Database Service (RDS) Creation in Amazon Web Services (AWS)**



### **AIM:**
To create and configure a relational database using Amazon RDS (Relational Database Service) in AWS.



### **EQUIPMENT REQUIRED:**

1. **Hardware:**
   - A computer with internet access.

2. **Software:**
   - Web browser (e.g., Chrome, Firefox).
   - AWS account with permissions to create RDS instances.

3. **Tools:**
   - AWS Management Console.



### **THEORY:**

**Amazon RDS (Relational Database Service)** is a fully managed database service that makes it easier to set up, operate, and scale a relational database in the cloud. It supports various database engines such as:

- **MySQL**
- **PostgreSQL**
- **MariaDB**
- **Oracle**
- **Microsoft SQL Server**

RDS automates tasks such as backups, patch management, and failover, which makes it ideal for applications requiring a reliable and scalable database.



### **ALGORITHM / PROCEDURE:**

#### **1. Create an RDS Instance:**

1. **Sign in to AWS Management Console:**
   - Log in to your AWS account via the [AWS Management Console](https://aws.amazon.com/console/).

2. **Navigate to RDS:**
   - In the AWS Console, search for **RDS** and select **Amazon RDS** from the services list.

3. **Create a Database:**
   - Click on **Create database**.
   - Choose **Standard Create** to customize the instance configuration.

4. **Choose a Database Engine:**
   - Select your desired database engine (e.g., **MySQL**, **PostgreSQL**, **MariaDB**, etc.).
   - For this example, let's use **MySQL**.

5. **Configure Database Settings:**
   - Enter the **DB Instance Identifier** (e.g., `mydatabase`).
   - Set a **Master Username** (e.g., `admin`) and **Master Password**. Make sure to store these credentials securely.
   - Choose the **DB instance class** (e.g., `db.t2.micro` for free tier).
   - Configure **Storage** (default size is 20 GB, but you can modify it based on needs).
   - Set **Storage Autoscaling** (optional).

6. **Configure Advanced Settings:**
   - Under **Network & Security**, select the **VPC** and subnet.
   - Choose **Public accessibility** as **Yes** if you want the database to be accessible from outside the VPC (for testing purposes).
   - Enable **Backup**, **Monitoring**, and **Encryption** based on requirements.
   - Set the **Database name** (e.g., `testdb`) if required.

7. **Create Database:**
   - Review the configurations and click **Create database**.
   - AWS will now provision the RDS instance. This may take several minutes.



#### **2. Connect to the RDS Instance:**

1. **Obtain the Endpoint:**
   - After the RDS instance is created, navigate to the **Databases** section in the RDS dashboard.
   - Select your database instance and copy the **Endpoint** (e.g., `mydatabase.cfsjckdbe1vb.us-east-1.rds.amazonaws.com`).

2. **Allow Inbound Traffic to the RDS Instance:**
   - Go to the **EC2 Dashboard** and navigate to **Security Groups**.
   - Select the security group assigned to the RDS instance.
   - Ensure the **Inbound rules** allow traffic on **port 3306** (MySQL default port), or the respective port for your selected DB engine.

3. **Connect Using MySQL Client (for MySQL RDS):**
   - Open your local terminal or command prompt.
   - Use the following command to connect to the RDS instance:
     ```bash
     mysql -h <RDS-Endpoint> -u admin -p
     ```
   - Replace `<RDS-Endpoint>` with the actual endpoint of your RDS instance (e.g., `mydatabase.cfsjckdbe1vb.us-east-1.rds.amazonaws.com`).
   - Enter the **Master Password** when prompted.

4. **Verify the Connection:**
   - Once connected, you can list databases:
     ```sql
     SHOW DATABASES;
     ```
   - You should see the `testdb` database (or any database you created during setup).



#### **3. Perform Basic Operations on the RDS Database:**

1. **Create a Database (Optional):**
   - If you didn't specify a database during setup, you can create a new one:
     ```sql
     CREATE DATABASE my_test_db;
     ```

2. **Create a Table:**
   - Use the following SQL command to create a table:
     ```sql
     CREATE TABLE users (
         id INT AUTO_INCREMENT PRIMARY KEY,
         name VARCHAR(100),
         email VARCHAR(100)
     );
     ```

3. **Insert Data:**
   - Insert some data into the table:
     ```sql
     INSERT INTO users (name, email) VALUES ('Alice', 'alice@example.com');
     INSERT INTO users (name, email) VALUES ('Bob', 'bob@example.com');
     ```

4. **Query Data:**
   - Retrieve the data from the `users` table:
     ```sql
     SELECT * FROM users;
     ```



### **OUTPUTS:**

- A relational database instance is created in Amazon RDS.
- Basic database operations (create, insert, select) are successfully executed.



### **RESULT:**

The relational database service (RDS) was successfully created and configured in AWS. A database instance was provisioned, and basic database operations such as creating tables, inserting, and querying data were successfully performed. The database is now ready for further use in applications.
