# Lab Exercise 03

## Cloud Scanning (CSPM) and Cloud Drift Detection

### Objective:

1.  I can create a new project for cloud scans
1.  I can onboard AWS account and connect to Tenable.io 
1.  I can create an AWS IAM role and policy
1.  I can understand how to run a real-time (cloud) scan
1.  I can understand setup Cloud-to-Cloud Drift
<!--
1.  I can understand how to scan a Terraform scan
1.  I can understand how to Code-to-Cloud Drift detection
-->
### Prerequisites
- Familiar with Tenable.cs Dashboard 
- Familiar with AWS Cloud Networking concepts
- Familiar with AWS Cloud Formation Templates
- Familiar with AWS IAM Roles and Policies

### Tasks

#### Retrieving Tenable Container Id
These steps are needed for the lab. An *unique* alphanumeric string is used as the ExternalId of the role.   The Tenable Container UUID should be used in this parameter.

**Reference:** In Tenable.io, navigate to Settings > License to get your container UUID. For more information, see <a href="https://docs.tenable.com/tenableio/Content/Platform/Settings/License/ViewLicenseInformation.htm" target="_blank" rel="nofollow noopener noreferrer"> View Information about Your Tenable.io Instance. </a>

Follow the steps below

1.  To find the Tenable Container UUID (**ExternalId**)

    1.  Log in to your Tenable.cs account
    1.  Go the the link <a href="https://cloud.tenable.com/tio/app.html#/settings/" target="_blank" rel="nofollow noopener noreferrer">ContainerID.</a>  <p>
    1.  Click on the **License** icon
    1.  Scroll down to the **Environment Information** container widget.    
  d.  Copy the value of **CONTAINER ID**.   This value as the  **ExternalId** parameter.   


#### Setup IAM Permission
##### Download YAML 
1.  Search for IAMroles in the Output Properties and copy the S3 URL link address

##### Create and run the Cloud Formation stack

1.  Navigate to AWS Console
1.  Select the **CloudFormation** service
1.  Click on **Create Stack->with New resources (standard)**
	  - Select **Template is Ready** 
    - Select **Amazon S3 URL**
    - Enter S3 URL link from Output Properities
1.	Click on **Next**
1.  In the window **Specify stack details:  
    1.  Enter the Stack name:  <u>**tenable-awsjams-role**</u>
    1.  Enter the **External Id** (this is the *Tenable Container Id*)
    1.  AllowVulnerabilityScanning should be set to **True** and will be used in a future lab to scan EC2 instances.
1.  Click **Next**
1.  *Accept* ***Acknowledgement*** and Click **Submit**

    
1.  When completed, you will use the ARN and ExternalId Values to connect Tenable to AWS  

#### Create a cloud connection on Tenable.cs

  a.  Save the **ARN** value from *Outputs* Properties  
  b.  Save the **ExternalId from *Parameters*</p><p>

1.  On Tenable.cs, create an AWS connection
1.  From the tenable.cs dashboard, goto the the left menu and click on the (+) symbol
1.  Click on *Connection->AWS connection*
1.  Select Onboard AWS account, and click **Continue**
1.  Choose **Public cloud** and click **Continue**
1.  Enter the **Read Only Role ARN** form the values saved above
1.  Enter the **External ID**, click on **Continue**
1.  *Create or Select* the **security_group_scan** project.  
    1.  If the project is not defined, click on **Add a project**
    1.  Enter **security_group_scan**  
    1.  Click on the *check box* to select the project
1.  Click on **CONNECT CLOUD ACCOUNT**

#### Perform AWS Cloud Run-time scan
1.  From the Tenable.cs dashboard, select the **PROJECTS & CONNECTIONS** tab
1.  Click on **Run scan->Cloud scan->Manage scan profiles**
1.  *Click* on **NEW SCAN PROFILE**
1.  Under <u>Scan profile name</u>, type in **Security Group Profile**
1.  In the search box, type in **Security Group**
1.  Click on the ***check box*** for **Security Group**
1.  Click the **Preview** button
1.  Click on the **Create Scan Profile** button
1.  Click on the vertical ellipse for <u>Security Group Profile</u> 
1.  Click on the **Run Scan** button, for the <u>Security Group Profile</u>, and select **Use as Default Scan**

1.  Exit from the dialog box and Click on **Findings** on the left menu.
1.  Click on **Misconfigurations**
1.  Notice all the Security Group misconfigurations found for all the AWS Security Groups.
1.  In the Search box, type in **SSH**
1.  Scroll until an Impacted resource name <u>imdstack-AwsInternalSecurityGroup</u> is found.

### Remediate Misconfigured Security Group
1. In the Output Properites, Copy the **Security Group ID** (eg.  *sg-XXXXXXXXXXXXXXXXX*) for the *Key* **AwsInternalSecurityGroup**.
1.  On AWS console, 
    1.  Navigate to **VPC->Security Group**
    1.  Search for the Security Group ID 
    1.  Select the *Security Group* and Select **Action->Edit Inbound rules**.  
    1.    Modify the ***SSH*** rule that contains  a the Source IP ( 0.0.0.0/0) to (10.1.1.0/24)  
  c.  Save the Rules.

1.  Rescan the project **security_group_scan**.
1.  Go back to **Findings->Misconfigurations**
1.  In the Search box, search for **SSH** or **22**
1.  Scroll until an Impacted resource name <u>imdstack-AwsInternalSecurityGroup</u>

## VALIDATION QUESTION

1.  Was <u>imdstack-AwsInternalSecurityGroup</u> found?

### Verify Drift

1.  Under **PROJECTS & CONNECTIONS**,
1.  Select the project, **security_group_scan**
1.  Is there a *Drift* count?  
1.  Click on the Drift value
1.  Select the Resource Type: **Security Group**
1.  Click on the Resource for <u>imdstack-AwsInternalSecurityGroup</u>
1.  Scroll down the Drift and expand the view the details.


## VALIDATION QUESTION
1.  Can you verify the changes in the configuration?

## END OF LAB