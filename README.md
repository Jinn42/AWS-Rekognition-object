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


Inbound rule:  
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/inboundrule.png"/></div>

Outbound rule:  
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/outboundrule.png"/></div>  

### launch the instance
Same as in [AWS_Jumpbox_Setting]（https://github.com/Jinn42/AWS_Jumpbox_Setting）


## Step2-Coniguration of backend server and link to Jupyter
### 1.Install Jupyter & open file in virtual machine
## -Check if python3 is installed
```
python3
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
jupyter notebook - - ip=0.0.0.0 
```

### 2.Use pew to link to Jupyter

- Install pew and create a new pew environment
```
pip3 install pew
```
```
pew new Jin2
```
- Exit and go back to thecpew environment
```
exit
```
```
pew workon Jin2
```
- Check current virtual environment
```
pew ls
```
- install pandans and then list everything and store them
```
pip3 install pandas
```
```
pip3 freeze > myEnv.tx
```
- link to Jupyter
```
pip3 install ipykernel

python3 -m ipykernel install --user --name=Jin2
```

## Step3-Clone Github repository
```
sudo apt-get install git

git clone https://github.com/Jinn42/AWS-Rekognition-object.git

```
### Find credential keys in vocareum:
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/AWS_credentials.png"/></div>  

Change the AWS credentials (access key id and secret access key) and pic_name in the reko.py code

## Step4 Test picture on Rekognition API (reko.py) & Result . 
### Tested picture
<div align=center><img width="600" height="300" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/Golden_Retriever_Hund_Dog.jpeg"/></div>  

### Result

<div align=center><img width="600" height="300" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/result.png"/></div>  
