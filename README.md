# CLCM3504 final exam 
1. Create an EC2 instance in AWS Academy console   
2. ssh -i "vpcshulintestkey.pem" ec2-user@ec2-3-87-80-186.compute-1.amazonaws.com
3. install httpd and docker server and start their services
    -sudo yum install httpd
    -sudo systemctl start httpd
    -sudo yum install docker
    -sudo systemctl start docker
    -sudo usermod -a -G docker ec2-user

4. Create github repository named clcm3504finalexam
    https://github.com/SHULINZ2023/clcm3504finalexam.git
5. Initialize previous project web application source code
    - git init --initial-branch=main
    - git add .
    - git commit -m "first commit"
    - git remote add origin https://github.com/SHULINZ2023/clcm3504finalexam.git
    - git push -u origin main
6. Create Dockerfile in root directory of source code 
    -- From httpd 2.4
    -- COPY . /var/www/html
7. Setup security environment variables in git repository  clcm3504finalexam
    EC2_SSH_KEY
    HOST_DNS
    TARGET_DIR
    USERNAME

8. Create workflow main.yml in repository clcm3504finalexam
    -checkout source code to github runner 
    -log in docker hub
    -build docker image  clcm3504finalexam
    -tag with shulinz/clcm3504finalexam:latest 
    -push to docker hub
    -log out docker hub
    -connect to ec2 via ssh
    -pull shulinz/clcm3504finalexam:latest
    -kill current container if shulinz/clcm3504finalexam:latest is running
    -start a container for image shulinz/clcm3504finalexam:latest
    -empty /var/www/html
    -copy all source code to /var/www/html 
