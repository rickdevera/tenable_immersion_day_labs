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
These steps are needed for the lab. An alphanumeric string to be used as the ExternalId of the role. The Tenable container ID should be used in this parameter.

  the unique ExternalId is a Cloud Formation parameter
1.  To find the Tenable container ID (**ExternalId**) 
    1.  Log in to your Tenable.cs account
    1.  Go the the link <a href="https://cloud.tenable.com/tio/app.html#/settings/" target="_blank" rel="nofollow noopener noreferrer">ContainerID.</a>  <p>
    1.  Click on the **License** icon
    1.  Scroll down to the **Environment Information** container widget.    
  d.  Copy the value of **CONTAINER ID**.   This value as the  **ExternalId** parameter   


#### Setup IAM Permission
##### Download YAML 
1.  Search for IAMroles in the Output Properties and copy the S3 URL link address

##### Create and run the Cloud Formation stack

1.  Navigate to AWS Console
1.  Search for CloudFormation and select **CloudFormation**
1.  Click on **Create Stack->with New resources (standard)**
	  - Select **Template is Ready** 
    - Select **Amazon S3 URL**
    - Enter S3 URL link from Output Properities
1.	Click on **Next**
1.  In the window **Specify stack details:  
    1.  Enter the Stack name:  <u>**tenable-awsjams-role**</u>
    1.  Enter the **External Id** (this is the *Tenable Container Id*)
    
1.  When completed, you will use the ARN and ExternalId Values to connect Tenable to AWS  

#### Create a cloud connection on Tenable.cs

  a.  Use the **ARN** value from *Outputs*  
  b.  Use **ExternalId from *Parameters*</p><p>

1.  On Tenable.cs, create an AWS connection and use the values above.
1.  Assign the AWS connection to **cloud_to_cloud_drift_demo**  

#### Setup Tenable.cs 
#### Create a new project
1.  From the Tenable.cs Dashboard
    1.  Create a new Project. 
	    * Name it differently like *cloud_to_cloud_drift_demo*
	    * Choose AWS as the Cloud Provider
#### Perform AWS Cloud Run-time scan
Tenable.cs will scan the cloud in run-time (CSPM) and report the findings.  This may take up to 2-3 minutes.

1.  On AWS, Cloud Run-time Scan configuration  
    a.  Configure and **Run the default cloud scan**
    b.  When complete, refresh (refresh icon)
the screen to displaly the results after the cloud scan is completed.
    
#### Configure and Perform a Cloud-to-Cloud Drift

1.  Log into Tenable.cs
2.  Go to the **Projects & Connections** tab
3.  Click on **Run Scan->Cloud Scan->Manage** Scan Profiles
4.  Click on **New scan profile** profile
5.  Edit the New profile and be sure Security Group, EC2 Instance, and VPC is checked and *uncheck (disable)* **Enable Vulnerability Scan**
6.  Set new profile as *Default*
7.  Run a *Cloud Scan** for the new profile
8.  Upon completed scan, goto Dashboard->Projects & Connections
9.  Click on **Set a Baseline** for the project **cloud_to_cloud_drift_demo**
10.  ***Record*** the **Drift** count
11.  On the AWS Jams Dashboard, click on Output Properties
    <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/output_properties.png" height="120" alt="refresh" />  
and copy the ID for <b>DriftSecurityGroup</b>.
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