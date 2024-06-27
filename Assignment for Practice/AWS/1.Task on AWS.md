### AWS Core Services Task Assignment

The following tasks will help trainees gain hands-on experience with key AWS services, focusing on EC2, S3, RDS, and IAM. These tasks will cover creating and managing resources, ensuring they understand the basics of AWS cloud computing.

### Prerequisites
- An active AWS account
- Basic knowledge of AWS Management Console
- AWS CLI installed and configured

### Tasks

1. **Amazon EC2 (Elastic Compute Cloud):**
   - Launch an EC2 instance.
     - Use the AWS Management Console to launch a t2.micro instance.
     - Choose Amazon Linux 2 as the AMI.
     - Create a new key pair for SSH access.
     - Configure the security group to allow SSH access (port 22) from your IP address.
   - Connect to the EC2 instance using SSH.
   - Install a web server (e.g., Apache) on the EC2 instance.
   - Access the web server from your browser to ensure it's running.

   ```bash
   # Example SSH command (replace with your instance's public DNS and key pair)
   ssh -i "your-key-pair.pem" ec2-user@ec2-xx-xx-xx-xx.compute-1.amazonaws.com

   # Example commands to install Apache on Amazon Linux 2
   sudo yum update -y
   sudo yum install httpd -y
   sudo systemctl start httpd
   sudo systemctl enable httpd
   ```

2. **Amazon S3 (Simple Storage Service):**
   - Create an S3 bucket.
     - Name the bucket (ensure the name is unique globally).
     - Choose the region closest to you.
   - Upload a file to the S3 bucket.
   - Make the file publicly accessible.
   - Retrieve the public URL of the file and access it from your browser.

   ```bash
   # AWS CLI commands to create a bucket and upload a file
   aws s3 mb s3://your-unique-bucket-name --region your-region
   aws s3 cp your-file.txt s3://your-unique-bucket-name/
   
   # Make the file public
   aws s3api put-object-acl --bucket your-unique-bucket-name --key your-file.txt --acl public-read
   ```

3. **Amazon RDS (Relational Database Service):**
   - Create an RDS instance.
     - Choose MySQL as the database engine.
     - Use the free tier option.
     - Set the master username and password.
     - Configure the security group to allow access from your IP address.
   - Connect to the RDS instance using a MySQL client (e.g., MySQL Workbench or the MySQL command-line client).
   - Create a database and a table, and insert some data.

   ```bash
   # Example MySQL command to connect (replace with your RDS endpoint and credentials)
   mysql -h your-rds-endpoint.rds.amazonaws.com -P 3306 -u your-username -p
   ```

   ```sql
   -- SQL commands to create a database, table, and insert data
   CREATE DATABASE mydatabase;
   USE mydatabase;
   CREATE TABLE mytable (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL
   );
   INSERT INTO mytable (name) VALUES ('John Doe'), ('Jane Smith');
   ```

4. **IAM (Identity and Access Management):**
   - Create a new IAM user.
     - Assign programmatic access (AWS Management Console access is optional).
     - Attach the "AmazonS3FullAccess" policy to the user.
   - Generate and download the access keys for the user.
   - Configure the AWS CLI with the new IAM user credentials.
   - Use the AWS CLI to list the contents of your S3 bucket.

   ```bash
   # AWS CLI command to configure with new IAM user credentials
   aws configure
   # Enter the access key ID and secret access key for the new IAM user

   # List the contents of the S3 bucket
   aws s3 ls s3://your-unique-bucket-name/
   ```

5. **Automation with AWS CloudFormation (Optional Advanced Task):**
   - Create a CloudFormation template to automate the deployment of an EC2 instance and an S3 bucket.
   - Use the AWS Management Console or CLI to create a stack using the template.
   - Verify the resources created by the CloudFormation stack.

   ```yaml
   # Sample CloudFormation template (YAML format)
   AWSTemplateFormatVersion: '2010-09-09'
   Resources:
     MyEC2Instance:
       Type: 'AWS::EC2::Instance'
       Properties:
         InstanceType: 't2.micro'
         ImageId: 'ami-0c55b159cbfafe1f0' # Amazon Linux 2 AMI
         KeyName: 'your-key-pair'
     MyS3Bucket
