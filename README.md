# Deployment-of-Amazon-clone-app
Deployment of Amazon clone app using Terraform and jenkins ci-cd

  ![image](https://github.com/574n13y/Deployment-of-Amazon-clone-app/assets/35293085/0612405a-77f5-4144-976c-6a2723a38951)


## Pre-requisite
  - aws account
  - basics of terraform and jenkins

    
## Completion steps →
  - Step 1 → Setup Terraform and configure aws on your local machine
  - Step 2 → Building a simple Infrastructure from code using terraform
  - Step 3 → Setup Sonarqube and jenkins
  - Step 4 → ci-cd pipeline
  - Step5 →Monitering via Prmotheus and grafana
  - Step 6 → Terraform Destroy

## Step 1 → Setup Terraform and configure aws on your local machine
  1. **Setup Terraform**
     - To install terraform copy and paste the below commands
     ```
     sudo su
     snap install terraform --classic
      which terraform
     ```
  2.  **Configure aws**
      - create an IAM user
      - go to your aws account and type IAM
      - click on user →create user
      - Give a name to your user and tick on provide user access to management console and then click on I want an IAM user option
      - choose a password for your user →click next
      - Attach the policies directly to your iam user → click next
      - click on create user
      - download your password file if it is autogenerated otherwise it is your’s choice
      - Now click on your IAM user →security credentials
      - scroll down to access keys and create an access keys
      - choose aws cli from the options listed
      - click next and download you csv file for username and password
      - go to your terminal and type →aws configure
      - Now it is ask to your access key and secret key for this open your csv file and paste the access and secret key and remain everything default
      - Now you are ready to configure aws from your terminal

 ## Step 2 → Building a simple Infrastructure from code using terraform
   1. go to folder → cd JENKINS-TF
   2. there are three files present main.tf, install_jenkins.sh , provider.tf
   3. open the file →vim Main.tf
   4. change this section → ami = # your ami id , key_name= #your key pair if any
      - Now run terraform commands →
      - main.tf includes userdata which links install_jenkins.sh file on which execution install jenkins,docker,trivy,and start the sonarqube container on port 9000
        ```
        terraform init
        terraform validate
        terraform plan
        terraform apply --auto-approve
        ```
      - Go to your aws console and checkout the ec2 instances
      - Here we see amazon app instance is created by terraform with the given configuration



  - 

  - 

  - 

  - 

  - 

  - 
