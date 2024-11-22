## **Experiment 6: Creation of a Web Application for Test Environment**



### **AIM:**
To create a web application in a test environment using AWS services (e.g., Elastic Beanstalk) or a local development server.



### **EQUIPMENT REQUIRED:**

1. **Hardware:**
   - A computer with internet access.

2. **Software:**
   - Web browser (e.g., Chrome, Firefox).
   - Text editor or Integrated Development Environment (IDE) (e.g., VS Code, Sublime Text).
   - Local web server (e.g., XAMPP, WAMP) or AWS account for deployment.

3. **Programming Tools:**
   - Frontend: HTML, CSS, JavaScript (optional frameworks like React or Angular).
   - Backend: Node.js, Python (Flask/Django), or PHP.
   - Database (optional): MySQL, PostgreSQL, or DynamoDB.



### **THEORY:**

A **test environment** is an isolated space where a web application can be developed, deployed, and tested before it is released to production. It ensures the code is functional and error-free under controlled conditions. Popular approaches include:

- **Local Test Environment**: Applications are tested on a local web server like XAMPP/WAMP.
- **Cloud-based Test Environment**: Deployed on platforms like AWS Elastic Beanstalk, which automatically manages infrastructure and resources for testing.

**AWS Elastic Beanstalk** simplifies application deployment by providing a managed environment for running web applications. It supports multiple languages and frameworks, such as Node.js, Python, and Java.



### **ALGORITHM / PROCEDURE:**

#### **1. Setup a Local Web Application Test Environment:**

1. **Install a Local Server (Optional):**
   - Install XAMPP or WAMP for local testing (if using PHP or MySQL).
   - Start the Apache and MySQL servers from the control panel.

2. **Create the Web Application:**
   - Create a project folder (e.g., `TestWebApp`).
   - Add an `index.html` file as the entry point.
   - (Optional) Add CSS, JavaScript, or backend code depending on requirements.

3. **Run the Application Locally:**
   - Place the project in the server’s `htdocs` folder (for XAMPP/WAMP).
   - Access the application in a browser using `http://localhost/TestWebApp`.



#### **2. Create and Deploy a Web Application in AWS Elastic Beanstalk:**

1. **Set Up AWS CLI (Optional):**
   - Install AWS CLI and configure it with your credentials:
     ```bash
     aws configure
     ```
     Enter your **Access Key**, **Secret Key**, region (e.g., `us-east-1`), and output format (e.g., `json`).

2. **Create the Web Application Code:**
   - Develop the web application using your preferred language/framework.
   - For example, a simple `app.py` for a Flask application:
     ```python
     from flask import Flask
     app = Flask(__name__)

     @app.route("/")
     def home():
         return "Welcome to the Test Environment!"

     if __name__ == "__main__":
         app.run(debug=True)
     ```
   - Save your project in a folder (e.g., `TestWebApp`).

3. **Zip the Application Files:**
   - Compress your application files into a `.zip` file for deployment.

4. **Deploy to Elastic Beanstalk:**
   - In the AWS Management Console, search for **Elastic Beanstalk**.
   - Click **Create Application**.
   - Enter an **Application Name** (e.g., `TestWebApp`).
   - Select a **Platform** (e.g., Python, Node.js, or PHP).
   - Upload the `.zip` file of your application.
   - Click **Create Application** to deploy.

5. **Test the Application:**
   - Once the application is deployed, AWS will provide a public URL.
   - Open the URL in a browser to test your application.



### **OUTPUTS:**

- The web application is successfully created and tested in the local environment or deployed to AWS Elastic Beanstalk.



### **RESULT:**

The web application was successfully created and deployed in the test environment. It was tested for functionality and confirmed to be operational.
