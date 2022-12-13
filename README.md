# tenable_immersion_day

Welcome to the lab Instruction!

### Requirements:

1.  AWS account - if you don't have one, Sign-up for free AWS account . All sevices in this lab are not covered under free tier, so it may incur some minor cost.
1.  Tenable Cloud Account -
1.  Github account - Sign-up for Github account www.github.com
1.  CloudFormation Template (needed for some labs)
  - EC2 instance for AA
  - Bastion/Guacamole Instance
  - Developer workstation (Windows Desktop)
1.  Laptop with Browser or RDP access


Instructor Led :
* AWS account 
								  
Self-paced :
If you want to run pre-requisite steps by yourself:
* AWS account - if you don't have one, Sign-up for [free AWS account](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc) . All sevices in this lab are not covered under free tier, so it may incur some minor cost.
* Follow the instruction in the labs below

   
Click the **Deploy to AWS** icons below to stand up the RDS database infrastructure. 

| Region | Launch Template |
| ------------ | ------------- | 
**N.Virginia** (us-east-1) | [![Launch CloudFormation](/ee_helper/assets/images/00-deploy-to-aws.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=dmslab-instructor&templateURL=https://s3.amazonaws.com/aws-dataengineering-day.workshop.aws/DMSLab_instructor_CFN.yaml) 

### What you'll do:

These labs are designed to be completed in sequence, and the full set of instructions are documented below.  Read and follow along to complete the labs. Our lab instructor will give you a high-level overview of the labs and help answer any questions.  Don't worry if you get stuck, we provide hints along the way.

__**Ensure your region is US East (N. Virginia)**__


* **Workshop Setup:** [Create working environment on AWS](#workshop-setup)
* **Lab 1:** PreCommmit Stage - IaC scan on Developer workstation
* **Lab 2:** PostCommit State - IaC scan on SourceCode
* **Lab 3:** CI/CD scan - Integration with CI/CD pipeline
* **Lab 4:** Cloud Scan/Drift Detection
* **Lab 5:** Agentless Assessment / Vulnerability Management
* **Cleanup** 




What you'll do:
These labs are designed to be completed in sequence, and the full set of instructions are documented below. Read and follow along to complete the labs. Our lab instructor will give you a high-level overview of the labs and help answer any questions. Don't worry if you get stuck, we provide hints along the way.

Ensure your region is US East (N. Virginia)

