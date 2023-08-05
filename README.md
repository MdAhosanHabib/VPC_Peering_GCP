
# VPC Peering in different regions and Proxy port connection on VMs setup in Google Cloud.

## Overview: 
In this project, we will create two Virtual Private Clouds (VPCs) on Google Cloud Platform and set up two virtual machines (VMs) in each VPC. We will then establish connectivity between the VMs to host an Nginx web server, allowing them to communicate securely by VPC peering.

## Outcome of this Project:
Create Two VPCs in separate regions on Google Cloud Platform.

Configure the IP ranges for each VPC to avoid overlapping.

Create VMs in Each VPC.

Choose suitable machine types and operating systems for the VMs.

Set Up Nginx on VMs.

Install Nginx web server to serve as the frontend servers.

Configure Firewall Rules: Create firewall rules for each VPC to allow HTTP (port 80) traffic between the VMs.
 Limit access to only the necessary ports and protocols to enhance security.

Establish VPC Peering: Create a VPC peering connection between VPC.

Allow communication between the VMs in both VPCs while keeping the networks isolated.

Test Connectivity: Verify that the Nginx web servers are accessible from another VM.

## Conclusion: 
By completing this project, we have successfully created two isolated VPCs on Google Cloud Platform, established connectivity between the VMs in different VPCs using VPC peering, and set up an Nginx web server. This project demonstrates how to build a secure and scalable infrastructure on GCP, allowing for potential expansion and adding additional services to meet various business requirements. Google Cloud Platform.



Now we are going to the main steps.

##
## Working Diagram:
<img width="491" alt="VPC_Peering_Port_Connect_GCP" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/490d9129-7f08-46ab-9922-363772880485">


##
## Creating VPC and Subnet:
1.	Creating vpc-proxy-ahosan on Region:

Name: vpc-proxy-ahosan.

Subnet: vpc-proxy-ahosan-subnet.

Region: us-central1.

IP Rnage: 10.0.10.0/24.

Private google access off.

Firewalls rules all selected.

Create now.
<img width="960" alt="VPC1-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/fa4c5140-412b-420f-a71d-0866e2ea1bf4">
<img width="960" alt="VPC1-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/3fa70230-7168-4769-ae81-7b9028807aa6">
<img width="960" alt="VPC1-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/a76d9499-0b0e-4c75-8d54-11ff32558b75">
<img width="960" alt="VPC1-4" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/d0ab7550-83c9-4464-8eba-0675b2c3d936">
<img width="960" alt="VPC1-5" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/3c75496a-a9b8-4c90-b037-6434ec31f084">
<img width="960" alt="VPC1-6" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/f2634bb1-7a7b-4749-ad5e-449570932366">



2.	Creating vpc-client-ahosan on Region:

Name: vpc-client-ahosan.

Subnet: vpc-client-ahosan-subnet.

Region: Us-east1.

IP Range: 172.16.10.0/24.

Private google access off.

Firewalls rules all selected.

Create now.
<img width="960" alt="VPC2-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/5be26839-f763-4870-a7ca-6ad8ee6c25e9">
<img width="960" alt="VPC2-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/fbc30486-9c7e-4b99-a72b-753bf9fc2e2b">
<img width="960" alt="VPC2-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/8bb898b6-7b44-4ab1-8a72-bb14ab251ddd">
<img width="960" alt="VPC2-4" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/a434dad4-9411-4611-926d-5484a714c63c">
<img width="960" alt="VPC2-5" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/5ed2699a-059d-4218-a2cb-9e7cb880da2b">
<img width="960" alt="VPC2-6" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/03fc9128-354f-44ee-8434-3ad613f0cee2">


##
## Creating VMs on VPCs:
1.	Creating vm-proxy-ahosan:

Name: vm-proxy-ahosan.

Region: us-central1(lowa)/us-central-a.

Network Interface: vpc-proxy-ahosan.

Subnet: vpc-proxy-ahosan-subnet.

Create now.
<img width="960" alt="VM1-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/13a03bee-b6f9-438b-a30f-4893e6c9a755">
<img width="960" alt="VM1-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/2124b164-a751-40ce-b226-2b524ef3e00f">
<img width="960" alt="VM1-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/2b56275f-8477-4be8-9f25-a5fb6ea52823">


2.	Creating vm-client-ahosan:

Name: vm-client-ahosan.

Region: Us-east1(South Carolina)/us-east1-b.

Network Interface: vpc-client-ahosan.

Subnet: vpc-client-ahosan-subnet.

Create now.
<img width="960" alt="VM2-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/a893d0b3-4319-42c7-ab7f-3bd3ebe4f04e">
<img width="960" alt="VM2-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/97ff2f69-525d-4d63-8b5a-e46e51784756">
<img width="960" alt="VM2-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/e1d3110e-9378-4efc-9584-16e5798e7e1e">

##
## Connecting vpc-client-ahosan and vpc-proxy-ahosan by VPC peering:
1.	vpc-client-vpc-proxy.

Your VPC net: vpc-proxy-ahosan.

Peered VPC net: vpc-client-ahosan.

Export subnet routes with public IP.

Create now.
<img width="960" alt="VPC-Peer1-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/1d1bec3a-d387-43c4-914d-2b4ff8e175a2">
<img width="960" alt="VPC-Peer1-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/2f9e7c54-f727-481a-a982-a3e84c5d4ad7">
<img width="960" alt="VPC-Peer1-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/099929c8-6897-49c5-99ca-dc436f8b72d2">


2.	vpc-proxy-vpc-client.

Your VPC net: vpc-client-ahosan.

Peered VPC net: vpc-proxy-ahosan.

Export subnet routes with public IP.

Create now.
<img width="960" alt="VPC-Peer2-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/e2c4ba49-d5a6-4d25-8b6d-365c447bb5cc">
<img width="960" alt="VPC-Peer2-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/1a0da10f-f753-49d9-8a93-ce8800e5edcc">
<img width="960" alt="VPC-Peer2-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/724c4de8-430e-44b6-8910-4c4e4dd72f29">



Ping the server!

Telnet will not available.

##
## Port allow from Client to Proxy:
1.	Go to Firewall.

Name: client-to-proxy-tcp-80.

Network: vpc-proxy-ahosan.

Trafic: ingress.

Source IP Range: 172.16.10.0/24.

TCP/80.

Create now.
<img width="960" alt="firewall1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/ea4edcb6-8ceb-41c1-ad92-ba86c8845686">
<img width="960" alt="firewall2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/9284e51e-bf66-47b1-b5a0-9b24dd4dfd0d">
<img width="960" alt="firewall3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/9a172032-c44c-40f7-9162-2eb07689c2c4">
<img width="960" alt="firewall4" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/80169e14-ba20-4b8c-a9ca-8e0465bf874d">
<img width="960" alt="firewall5" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/1746665e-f395-4ce0-b3c6-a36d96cecec2">

##
## Install NGINX on vm-proxy-ahosan:
```bash
sudo apt install telnet #in two VMs
sudo apt install nginx #in proxy-VM only
telnet 10.0.10.2 80 #from client-VM
```
<img width="960" alt="SSH-1" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/c2effba3-e1bc-4e2a-927f-1e1137f4db49">
<img width="960" alt="SSH-2" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/ee78baa1-8ddb-45a6-a28b-3d5dd25f7dd4">
<img width="960" alt="SSH-3" src="https://github.com/MdAhosanHabib/VPC_Peering_GCP/assets/43145662/5497a79f-4257-49ea-af53-7813fa0ad86d">


##
## To test Nginx connection is okay from vm-client-ahosan run the command:

```bash
curl -I http://10.0.10.2
    #HTTP/1.1 200 OK
    #Server: nginx/1.14.1
    #Date: Sat, 05 Aug 2023 06:40:04 GMT
    #Content-Type: text/html
    #Content-Length: 4057
    #Last-Modified: Tue, 21 Dec 2021 19:41:19 GMT
    #Connection: keep-alive
    #ETag: "61c22ddf-fd9"
    #Accept-Ranges: bytes
```

##
Congratulations! Your target has been reached.

Thank you from Ahosan Habib.
##
