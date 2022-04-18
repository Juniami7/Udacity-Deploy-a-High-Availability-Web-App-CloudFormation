# Udacity-Deploy-a-High-Availability-Web-App-CloudFormation
Project 2

Deploy a high-availability web app using CloudFormation

This project deploys a high-availability web app using Infrastructure as Code (IaC) with AWS Cloudformation scripts.

Scenario:
Your company is creating an Instagram clone called Udagram. 
Developers want to deploy a new application to the AWS infrastructure. 
You have been tasked with provisioning the required infrastructure and deploying a dummy application, along with the necessary supporting software. 
This needs to be automated so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.


Project Files
	• /CloudFormation Stacks: 
		○ network-params.json: Parameters file for network cloudformation stack.
		○ network.yml: CloudFormation template for creating networking resources for this project.
		○ servers-params.json: Parameters file for servers cloud formation stack.
		○ servers.yml: CloudFormation template for creating servers for this project.
	• Infrastructure_Diagram: This folder contains the Infrastructure Diagram outline for the Project (Network and Resources).
	• /Screenshots: This folder contain screenshots of whole workflow status
	• /Scripts: This folder contains scripts to create, delete and update CloudFormation stack


Project Setup
1. To create network resources using cloudformation template, run the command(s) below. 
		Resources created:
			○ VPC
			○ Subnets
			○ Route Tables
			○ Routes
			○ Internet Gateway
			○ NAT Gateways
				Outputs the following:
					• VPC ID
					• VPC Public and Private Route Tables
					• List of public subnets
					• List of private subnets
					• Each of public and private subnet ID
			
		# $ scripts/create-stack.sh ProjectNetwork-stack Network.yml Network-params.json #

2. To create server resources using cloudformation template which pulls source code from S3 bucket automatically while starting, run the below command. 
		Resources created:
			○ Security Groups
			○ IAM Role, Instance Profile
			○ Launch configuration
			○ Target Group
			○ Auto Scaling Group
			○ Load Balancer

		# $ scripts/create-stack.sh ProjectServers-stack Servers.yml Servers-params.json #

Once the above steps are complete, you can find the URL of application in the outputs section of the ProjectServers Cloudformation Stack. Example:
https://github.com/Juniami7/Udacity-Deploy-a-High-Availability-Web-App-CloudFormation/tree/main/Screenshots
