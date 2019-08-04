Connect to the AWS Host with private Key :
ssh -i <private key> -l <os> <IP>
ssh -i devops.pem -l centos <IP>

--Installing wget
sudo yum install wget -y

--Download terraform from web : 
wget https://releases.hashicorp.com/terraform/0.12.6/terraform_0.12.6_linux_amd64.zip 

sudo yum install unzip -y

unzip terraform_0.12.6_linux_amd64.zip

sudo mv terraform /bin

terraform -v

sudo yum install python -y

Please login to AWS and search with IAM 
    You need to create Identity and Access Management(IAM) in AWS to connect to terraform
1. Select Add User: TestUser
2. Access type: Programmatic access and then click next
3. Set a Permission on
    3.1 Creat Group
    3.2 Group Name : Test_Admin & select AdministratorAccess and then Create Group
    3.3 Then proceed next steps and then will create a Access key ID and Secreate access key

For AWS CLI, you need to install python2-pip Installtion of pip has some issue so 
First install below command and the procced

sudo yum --enablerepo=extras install epel-release

sudo yum install python2-pip -y

sudo pip install awscli 
-- Configure the AWS configuration 
$ aws configure
    AWS Access Key ID [None]: <>
    AWS Secret Access Key [None]: <>
    Default region name [None]: <us-east-2>
    Default output format [None]: 
Provide all above details 

It will give all the details of 
$ aws ec2 describe-instances
--Out put in table format: 
[centos@ip-172-31-36-88 ~]$ aws ec2 describe-instances --output table


terraform init;terraform plan;terraform apply;terraform  destroy



