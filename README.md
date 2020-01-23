# AWS-Rekognition-object
## Objective: detect the object by the AWS Rekognition API in a setted distant machine
## Step1-set up and launch the instance
### Set up the configuration

create a vpc with /16 IPv4 CIDR block;  
create 1 public subnet inked to the VPC with /24 IPv4 CIDR block within one AZ；  
create 1 Internet Gateway associated with the public subnet；  
1 Route table;  

<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/routetable.png"/></div>

1 Ubuntu instances (Back-end_server);
Create an instance: Back-end_server (public) with type Ubuntu Server 18.04 LTS (HVM) (ami-04b9e92b5572fa0d1), type t2.micro, enable Auto-assign Public IP to avoid EIP creation (no flexibility needed here) and configure storage to 10GiB (could be less or more depending on your needs).

1 Security groups;  
Inbound rule:  
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/inboundrule.png"/></div>

Outbound rule:  
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/outboundrule.png"/></div>  

###launch the instance
Same as in [AWS_Jumpbox_Setting]（https://github.com/Jinn42/AWS_Jumpbox_Setting）


## Step2-Coniguration of backend server  

## -Check if python3 is installed
```
python3
```
## -Open python file from local file to virtual machine in another terminal
```
cd Downloads
scp -i keypair.pem asdfgh.py
ubuntu@ec2-54-144-146-229.compute-1.amazonaws.com:
```
## -Then check in virtual machine
```
ls
python3 name.py
```
## -Install pip
```
sudo apt-get update -y
sudo apt-get install python3-pip
```
## -Install Jupyter
```
sudo pip3 install jupyter
```
## -Open Jupyter Notebook
```
nohup jupyter notebook - - ip=0.0.0.0 &




## Step3-Clone Github repository

## Test picture on Rekognition API 

