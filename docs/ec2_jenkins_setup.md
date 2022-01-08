### Download and install Jenkins
To download and install Jenkins
- Add the Jenkins repo using the following command: `[ec2-user ~]$ sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo`
- Import a key file from Jenkins-CI to enable installation from the package:`[ec2-user ~]$ sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key`
- use the following command to perform a quick software update:`[ec2-user ~]$ sudo yum update –y`

- Install Jenkins:

~~~
[ec2-user ~]$ sudo yum install jenkins java-1.8.0-openjdk-devel -y

Error: Package: jenkins-2.306-1.1.noarch (jenkins)
           Requires: daemonize 
 Run this comment to resolve the above error
 $ sudo amazon-linux-extras install epel
 [ec2-user ~]$ sudo systemctl daemon-reload
 - Start Jenkins as a service:

[ec2-user ~]$ sudo systemctl start jenkins

-You can check the status of the Jenkins service using the command:

[ec2-user ~]$ sudo systemctl status jenkins
~~~
#### Configure Jenkins
Jenkins is now installed and running on our EC2 instance. To configure Jenkins:

Connect to `http://<your_server_public_DNS>:8080` from your favorite browser.
You will be able to access Jenkins through its management interface:
![onlock jenkins](./images/jenkins/unlock.png)

- As prompted, enter the password found in `/var/lib/jenkins/secrets/initialAdminPassword`

Use the following command to display this password:

`[ec2-user ~]$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
copy the password and paste it in the above password section.

The Jenkins installation script directs you to the Customize Jenkins page. Click Install suggested plugins.
![pluginsjenkins](./images/jenkins/jenkins.png)

Once the installation is complete, Create First Admin User, click Save and Continue.
![userjenkins](./images/jenkins/username.png)
![userjenkins](./images/jenkins/finaljen.png)
![userjenkins](./images/jenkins/finalsetup.png)

We are now ready to use EC2 instances as Jenkins agents.


#### Delete your EC2 instance
Clean up
After completing this tutorial, be sure to delete the AWS resources that you created so that you do not continue to accrue charges.
In the left-hand navigation bar of the Amazon EC2 console, choose Instances.
Right-click on the instance you created earlier and select Terminate.
