# Lab Exercise 04

## Scanning for Vulnerabilities


### Objective:

- I can access integrate (add) a Github repository with a Tenable.cs project
- I can clone a Github repository
- I can scan IaC
- I can identify Misconfigurations
- I can remediate code and create Pull Requests
- I can setup Auto Remediation

### Prerequisites
- Tenable.io account
- Prior knowledge of GitHub - https://docs.github.com/en/get-started/quickstart/hello-world
- Understand use cases of Infrastructure as Code (IaC)
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser

### Tasks

#### 1.  Preparation

1.  On the AWS console, create an snapshot for the instance volume   
  a.  Go to the **EC2 Dashboard**    
  b.  Go to **Elastic Block Store->Snapshot**  
  c.  Click on **Create snapshot**  
  d.  Click on the **Instance** radio button      
  e.  Click on the ***Instance ID*** pulldown menu 
  f.  Select the Instance for **AA_EC2_Demo**
  g.  Enter a description:  **Agentless Demo EC2 Snapshot**   
  h.  Click on **Create snapshot**    
    This may take a few menutes   
  g.  Click the refresh button and **WAIT** for the <u>Snapshot Status</u> to display status as **Completed**.  


#### Setup a Project 
3.  In Tenable.cs, create a project  
a.  Click on the (+) button on the left menu  
b.  Enter the project name: **agentless_assessment_awsjam_demo**  
c.  Select **AWS**  
d.  Click on **Create**

#### Scan the project

This will scan the snapshot of the EC2 instance

4.  Associate the Project **agentless_assessment_awsjam_demo** with a cloud account  
  a.  Click and open the project:  **agentless_assessment_awsjam_demo**  
  b.  Click on the pencil icon for Cloud Accounts  
  c.  Select and Save the cloud account that was created in Task 3.  (ie *arn:aws:iam::*:role/TenableTrustRole*)  
  d.  From the Tenable.cs Dashboard, Click on **HOME-PROJECTS & CONNECTIONS**
5.  Create a scan profile for **agentless_assessment_awsjam_demo**.  
  a.  Select the project **agentless_assessment_awsjam_demo**, click on **Run Scan->Cloud Scan->Manage Scan Profiles**.    
  b.  Click on **New Scan Profile** button.  
  c.  Enter an <u>Scan Profile name:</u>  **AA_profile_demo**  
  d.   Expand (**down arrow/caret** on the right of the options) to and enable **Compute->EC2 Instance**  
  e.  Expand and enable **Security, Identify and Compliance->Security Group**  
  f.  For **Enable Vulnerability Scan**, click and set Toggle switch to *ON*  
  g.  Click on **Create Scan Profile**
  h.  Click on **Run Scan->AA_profile_demo**

Note:  Scan may take several minutes to complete.  

6.  Find the Plugin ID associated with reported vulnerabilities  
  a.  Click to **Findings->Vulnerabilities** to display vulnerabilities found.    
  b.  Click on **Filters** and pick the project (**agentless_assessment_awsjam_demo**)  
  c.  Click on the **Vulnerability Name**  (See image)
<img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/plug-in.png" height="450" />  
