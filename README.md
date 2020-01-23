# AWS-Rekognition-object
## Objective: detect the object by the AWS Rekognition API in a setted distant machine
## Step1-set up and launch the instance
create a vpc with /16 IPv4 CIDR block;  
create 1 public subnet inked to the VPC with /24 IPv4 CIDR block within one AZ；  
create 1 Internet Gateway associated with the public subnet；  
1 Route table;  
Inbound rule:  
<div align=center><img width="400" height="150" src="https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/inboundrule.png"/></div>

Outbound rule:  
![](https://github.com/Jinn42/AWS-Rekognition-object/blob/master/pic/outboundrule.png)


1 Ubuntu instances (Back-end_server)
1 Security groups
## Step2-Coniguration of backend server

## Step3-Clone Github repository

## Test picture on Rekognition API 
```
nohup jupyter notebook - - ip=0.0.0.0 &
```
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/openjupyter.png)
