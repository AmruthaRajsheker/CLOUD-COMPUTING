### **Experiment 6: Creation of a Web Application for Test Environment Using AWS Services**



### **AIM:**
To create and deploy a web application in a test environment using AWS services like Elastic Beanstalk, S3, and RDS.



### **EQUIPMENT REQUIRED:**

1. **Hardware:**
   - A computer with internet access.

2. **Software:**
   - Web browser (e.g., Chrome, Firefox).
   - AWS account with permissions for Elastic Beanstalk, S3, and RDS.

3. **Programming Tools:**
   - A web application framework (e.g., Flask, Django, or Node.js).
   - AWS CLI (optional for deployment).



### **THEORY:**

AWS provides various services to create and deploy web applications in a cloud-based test environment. The most commonly used services are:

1. **Amazon Elastic Beanstalk:** A fully managed service that automatically handles the deployment, scaling, and management of applications.
2. **Amazon S3:** A scalable storage service for hosting static files or media.
3. **Amazon RDS:** A managed relational database service for storing application data.

These services simplify creating a test environment while ensuring scalability and reliability.



### **ALGORITHM / PROCEDURE:**

#### **1. Create the Web Application Locally:**

1. **Develop the Application:**
   - Create a simple application using a framework like Flask (Python), Node.js, or Spring Boot (Java).
   - Example for Flask (`app.py`):
     ```python
     from flask import Flask
     app = Flask(__name__)

     @app.route("/")
     def home():
         return "Welcome to the Test Environment using AWS!"

     if __name__ == "__main__":
         app.run(debug=True)
     ```

2. **Install Required Dependencies:**
   - Create a `requirements.txt` file (for Python):
     ```
     Flask==2.0.1
     ```

3. **Test Locally:**
   - Run the application locally to ensure it works:
     ```bash
     python app.py
     ```
   - Access it in a browser at `http://127.0.0.1:5000`.



#### **2. Create and Configure the AWS Environment:**

##### **A. Set Up AWS Elastic Beanstalk for Deployment:**

1. **Sign in to AWS Console:**
   - Log in to the [AWS Management Console](https://aws.amazon.com/).

2. **Create a New Elastic Beanstalk Application:**
   - Search for **Elastic Beanstalk** in the AWS console.
   - Click **Create Application**.
   - Enter an **Application Name** (e.g., `TestWebApp`).

3. **Select Platform and Application Code:**
   - Choose a platform (e.g., **Python**, **Node.js**, or **PHP**).
   - Upload your application code as a `.zip` file (containing `app.py`, `requirements.txt`, and other files).

4. **Launch the Application:**
   - Click **Create Application**.
   - Wait for Elastic Beanstalk to provision the environment.

5. **Access the Application:**
   - Once deployed, AWS provides a public URL to access the application.



##### **B. Use Amazon S3 for Static File Hosting (Optional):**

1. **Navigate to S3:**
   - In the AWS Console, search for **S3** and click **Create bucket**.

2. **Create and Configure the Bucket:**
   - Enter a unique bucket name (e.g., `testwebapp-static-files`).
   - Choose a region (e.g., `us-east-1`).
   - Enable public access (if required for static files).

3. **Upload Static Files:**
   - Upload files like images, CSS, or JavaScript to the bucket.

4. **Access Files:**
   - Use the object URL provided by S3 to access static files.



##### **C. Set Up a Database with Amazon RDS (Optional):**

1. **Navigate to RDS:**
   - In the AWS Console, search for **RDS** and click **Create Database**.

2. **Create a Database Instance:**
   - Select **Standard Create** and choose a database engine (e.g., MySQL, PostgreSQL).
   - Configure settings like instance type (e.g., `db.t2.micro`) and storage size.

3. **Connect the Application to the Database:**
   - Update your application code with the RDS database endpoint:
     ```python
     import mysql.connector
     conn = mysql.connector.connect(
         host="your-rds-endpoint.amazonaws.com",
         user="admin",
         password="password",
         database="testdb"
     )
     ```



#### **3. Test the Deployed Application:**

- Access the Elastic Beanstalk application using the public URL provided.
- Ensure all components (e.g., database connectivity and static file access) are functional.



### **OUTPUTS:**

- A web application deployed to AWS Elastic Beanstalk.
- Static files hosted on Amazon S3 (if configured).
- Database configured with Amazon RDS (if used).



### **RESULT:**

The web application was successfully deployed in a test environment using AWS Elastic Beanstalk, with optional integration of S3 for static files and RDS for database storage.
