## **Experiment 2: Create an Account in AWS, Set Up a Root User, and an IAM User**



### **AIM:**
To create an account in AWS, set up the root user, and create an IAM user with specific permissions.



### **EQUIPMENT REQUIRED:**

- A computer with internet access.
- Web browser (e.g., Chrome, Firefox).
- AWS account details (email address).



### **THEORY:**

- **Root User**: The primary account holder with full administrative privileges.
- **IAM User**: A user with specific, limited permissions created using AWS Identity and Access Management (IAM).



### **ALGORITHM / PROCEDURE:**

1. **Create an AWS Account:**
   - Navigate to [AWS Sign Up](https://aws.amazon.com/) and click **Create a Free Account**.
   - Enter your email, password, and account name.
   - Provide payment details (AWS Free Tier is available).
   - Confirm identity via phone number.
   - Complete the registration and sign in.

2. **Sign in to AWS Management Console as Root User:**
   - After registration, sign in using your root user credentials.

3. **Enable MFA for Root User (Optional but Recommended):**
   - Navigate to **IAM Dashboard** → **Root Account** → **Multi-Factor Authentication** → **Activate MFA**.

4. **Create an IAM User:**
   - In the AWS Management Console, search for **IAM**.
   - Click on **Users** → **Add user**.
   - Enter a username (e.g., `newuser`), select **Access type** (Programmatic or Console access).
   - Click **Next: Permissions**.

5. **Assign Permissions:**
   - Choose **Attach policies directly** (e.g., **AdministratorAccess**).
   - Click **Next: Tags** → **Next: Review** → **Create user**.

6. **Download Credentials:**
   - Note the **Access Key ID** and **Secret Access Key** (for programmatic access).
   - Download the credentials as a CSV file.

7. **Test IAM User Access:**
   - Sign out of the root account.
   - Sign in with the IAM user's credentials to verify access.



### **OUTPUTS:**

- AWS account and root user are successfully set up.
- IAM user is created with specified permissions.



### **RESULT:**

The AWS account was created, the root user was set up, and an IAM user with appropriate permissions was created successfully. The IAM user is able to access AWS resources.
