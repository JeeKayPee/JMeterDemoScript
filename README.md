# For usage, please discuss with your faculty


1. Login to AWS account
2. Create EC2 machine - Ubuntu - T2.Micro. Open Security Group 8080
3. SSH into the machine
4. sudo apt update && sudo apt install docker.io --yes

5. Execute the following on the command line

# create a network for containers to communicate
sudo docker network create prestashop-net
# launch mysql 5.7 container
sudo docker run -ti --name some-mysql --network prestashop-net -e MYSQL_ROOT_PASSWORD=admin -p 3307:3306 -d mysql:5.7
# launch prestashop container
sudo docker run -ti --name some-prestashop --network prestashop-net -e DB_SERVER=some-mysql -p 8080:80 -d prestashop/prestashop:1.6

6. Launch the AWS_EC2_IP:8080 on your browser

This will launch the prestashop installer

7. Click on Next
Select the checkbox for agree and click on next

- Shop name - whatever
- Main Activity - Fashion and accessories
- Country - United States (Hard coded)
- Shop timezone - US/Eastern (Hard coded)
- Enter dummy information for First name, Last name, E-mail address, Shop password and Re-type to confirm
- Click on Next

Database server address - some-mysql
Database password - admin
Click on "Test your database connection now"
Click on Attempt to create the db automatically
	>>Database is created
Click on Next

The wizard will install the app

Launch a new browser tab - IP:8080 - the website will be running


Download and install JMeter on local machine or use a Windows 10 Server machine (hosted on AWS EC2)

Download Jmeter from the JMeter website
Extract the zip file
Browse to apache-jmeter-5.4.3/bin
Windows - double click on jmeter.bat
Mac/Linux - sh jmeter.sh

JMeter GUI will be displayed

Download the script from https://github.com/JeeKayPee/JMeterDemoScript

Using the JMeter GUI, load the script file
Click on the run button to execute the script
Examine the listeners for results. 




