# Web Hosting with AWS EC2 and Nginx
 This project involves hosting of website on a virtual machine in the cloud.
## Launch EC2 Instance 
1. Log in to the AWS Mnangement Console.
2. On the serach bar, search for EC2.
3. Click on instances.
4. Name your instance.
5. Choose Ubuntu AMI.
6. Choose t2 micro instance type.

![Image showing instance configuration](/Instance%20Config.png)
7. Create a key pair and save it.

![Image showing new keypair creation](/New%20Keypair.png)
8. Leave network setting and Advanced details as default
9. Set configuration setting to 8GB.
10. Launch instance.

![Image showing instance launch](/Launch%20Instance.png)
## Configure Security Group
1. Click on the newly created instance.
2. Scroll down to security and click on the security group link.

![Image showing security group](/Security%20Group.png)
![Image showing security group link](/Security%20Group%20Link.png)

3. Edit inboud rule to allow SSH,HTTP and HTTPs traffic from anywhere IPV4

![Image showing inbound rule edit](/Edit%20Inbound%20Rule.png)

4. Leave outbound rule as default to allow all traffic.

![Image showing outbound rule](/Outbound%20Rule.png)
## Connect Instance
1. Connet to your instance once the status check is passed. 

![Image showing status check passed](/Instance%20Check%20Passed.png)

2. Connect to your instance via SSH Client using its public DNS.

![Image showing instance connection](/Connect%20Instance.png)

3. Copy the code **ssh-i "keypem" ubuntu@"public DNS"** i.e **ssh-i "starboot.pem" ubuntu@ec2-54-78-208-141.eu-west-1.compute.amazonaws.com** to your gitbash.

![Image showing instance connection on gitbash](/SSH%20Connect%20on%20Git.png)
![Image showing ubuntu running](/Ubuntu%20running.png)
## Update, Install and Run Nginx on GitBash
1. Update the instance using
```sudo yum update```
2. Install, run, and enable the nginx package
```sudo yum install nginx```
```sudo systemctl stat nginx```
```sudo systemctl enable nginx```

![Image showing nginx running](/nginx%20running.png)

3. Test if nginx is running on the instance by running the instance public IP via browser.

![Image showing successful running of nginx on the browser](/Nginx%20tested%20on%20browser.png)

4. Get into the nginx path using
```cd /var/www/html``` OR ```cd /usr/share/nginx/html```
5. Wget the website content.
```sudo wget link of website to host```
6. check if unzip is install on the gitbash
```unzip -v```
7. If no, install unzip
```sudo apt install unzip```
8. unzip the zipped file
```sudo unzip name of file```

![Image showing file unzip](/unzip%20file%20on%20git.png)

9. move everything inside the file to path
```sudo move foldername/* destination```
10. Test site with instance public IP.

![Image showing site live](/Startbootstrap%20Live.png)