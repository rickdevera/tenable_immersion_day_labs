# Lab Exercise 03

## Cloud Scanning (CSPM) and Cloud Drift Detection

### Objective:

1.  I can create a new project for cloud scans
1.  I can onboard AWS account and connect to Tenable.io 
1.  I can create an AWS IAM role and policy
1.  I can understand how to run a real-time (cloud) scan
1.  I can understand setup Cloud-to-Cloud Drift detection

1.  I can understand how to scan a Terraform scan
1.  I can understand how to Code-to-Cloud Drift detection

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
1.  Select **security_group_scan** project.  
    1.  If the project is not defined, click on **Add a project**
    1.  Enter **security_group_scan**  
    1.  Click on the *check box* to select the project
1.  Click on **CONNECT CLOUD ACCOUNT**

#### Perform AWS Cloud Run-time scan
1.  From the Tenable.cs dashboard, select the **PROJECTS & CONNECTIONS** tab
1.  Click on **Run scan->Cloud scan->Manage scan profiles->System default AWS cloud scan profile**

### VALIDATION QUESTION ###
1.  What scan options are enabled in the default policies?

#### Scan a Security Group Profile
1.  From the Tenable.cs dashboard, select the **PROJECTS & CONNECTIONS** tab
1.  Click on **Run scan->Cloud scan->Manage scan profiles**
1.  On the **System default AWS cloud scan profile** click on the vertical ellipse on the right side and select **Duplicate**
1.  Clear all the selections, by clicking on **Select all**, then **Clear all** in the **Cloud config assessment options**.
1.  In the search bar, type in **Security Group**
1.  Click on the ***check box*** for **Security Group**
1.  Click Save
1.  Run the Scan

1.  Click on **Findings** on the left menu.
1.  Click on **Misconfigurations**
1.  Notice all the Security Group misconfigurations found for all the AWS Security Groups.

## VALIDATION QUESTION 
1.  Which policy groups are applied to the misconfiguration?
1.  How do you select a NIST policy as the baseline scan?


### Testing for Drift

1.  Create a new project, **cloud_to_cloud_drift_demo**
1.  Under **PROJECTS & CONNECTIONS**, *click* on **Cloud Accounts**
1.  Click on **Assign Project**
1.  Select the project, **cloud_to_cloud_drift_demo**
    
#### Configure and Perform a Cloud-to-Cloud Drift


1.  Click on **Set a Baseline** for the project **cloud_to_cloud_drift_demo**
1.  ***Record*** the **Drift** count
1. In the output properites, Copy the ID for <b>DriftSecurityGroup</b>.
12.  On AWS console, search for the Security GroupId
  a.  Modify the **Security Group->Inbound rules**.  
  b.  Modify the rule with a the Source IP ( 10.0.0.0/16) to (0.0.0.0/0)  
  c.  Save the Rules.

13.  ReRun a Cloud scan
14.  Verify Cloud Drift  
a.  Upon completion of scan, be sure to *refresh* 
the screen to displaly the results after the cloud scan is completed.   

</p>

### VALIDATION QUESTION

1.  How may ***Drifts*** were found? 