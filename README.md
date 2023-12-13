CLCM 3504 Final Exam: Upgrading TechCo Company’s Website with Dockerization.

1.	Instructions on how to set up the project:
•	Create a public repository in GitHub and add a README file in it.
•	Initialize the Git repository into your project directory and run git init, then add all the files using git add . and commit changes using git commit -m “Initial Commit”. Now, push the code to GitHub using git push -u origin main.
•	Now, launch an EC2 instance with Amazon Linux 2 AMI and add rules for HTTP (port 80) and SSH (port 22) traffic.
•	Connect to the EC2 Instance using: ssh -i <your-key.pem> ec2-user@<instance-ip>
•	To update Apache Web Server and Git, use: sudo yum update -y, to install the Apache web server: sudo yum install httpd -y, to start the Apache service: sudo service httpd start. Now, install Git using: sudo yum install git -y.
•	Now, set up your workflow to trigger the CI/CD process by adding a .yml file to it. The workflow created in .yml file will trigger on every push to the branch and attempt to deploy to the EC2 instance. Add in all your secrets.
•	Now, in your project directory, create a Docker file and add the contents of the project.Now,  build a docker image using: docker build -t image-name  and We will transfer the local image to EC2.
•	It should be all good to host the website now.

Automatic Deployment:
For every change pushed to the main branch, a Docker image is built automatically, and the image is pushed to the Docker. GitHub actions access the EC2 instance to pull that Docker image and try to stop and remove the old version of the Docker Container by using new Docker image version that was pulled before.

Challenges faced:
For this exam, I faced challenges in Dockerization. Understanding the concepts of Docker image and container was initially confusing for me and I ended up with getting a lot of errors. I also faced issues while deploying the docker image to EC2, but somehow, I was able to find the reason behind the issues and was able to successfully host the website.
 
