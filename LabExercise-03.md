# Lab Exercise 03

## Cloud Scanning (CSPM)

### Objective:

1.  I can create a new project for cloud scans
1.  I can onboard AWS account and connect to Tenable.io 
1.  I can create an AWS IAM role and policy 
1.  I can understand setup Cloud-to-Cloud Drift detection

### Prerequisites

### Tasks

#### Create a new project
1.  Ensure you're in Cloud Security.
	* In the left navigation bar, click Cloud Security. 
1.  Create a new Project. 
	* Name it differently like *cloud_to_cloud_drift_demo*
	* Choose AWS as the Cloud Provider

#### Setup IAM Permission
1.  Navigate to AWS Console
1.  Search for CloudFormation in the search, and select CloudFormation
1.  Click on Create Stack
	- Keep the *Template is ready*
	- Copy and paste the S3 url from Output Properties
1.	Click on Next
1.	Specify Stack details
	  -  Retrieve the Tenable Container ID and insert to ExternalID
1.  Click on Next, Review, and Submit

#### Onboard AWS Account

1.  On AWS, add a cloud account (connection) to Tenable.cs
2.  On the AWS console, **Cloud Formation->Create a Stack** and use the Amazon S3 URL template: 
https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/aa_role.yaml

This will create an IAM role and policy (to be used later) to authorize connection between Tenable.cs and AWS.  

3.  In the window **Specify stack details:  
  a.  Enter the Stack name:  **tenable-awsjams-role**
  b.  Enter the **External Id**.    
  c.  Follow the next steps to find the **ExternalId**  
  d.  Go the the link <a href="https://cloud.tenable.com/tio/app.html#/settings/license/" target="_blank" rel="nofollow noopener noreferrer">ContainerID.</a>  <p>
  b.  Click on **License**  
  c.  Scroll to the **Environment Information** widget.  </p><p><img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/container_id.png" height="250" />    
  d.  Copy the value of **CONTAINER ID** and input the value into the parameter **ExternalId** on the   
    
4.  Values needed to connect Tenable to AWS  
  a.  Use the **ARN** value from *Outputs*  
  b.  Use **ExternalId from *Parameters*</p><p>

5.  On Tenable.cs, create an AWS connection and use the values above.
6.  Assign the AWS connection to **cloud_to_cloud_drift_demo**  

#### Perform AWS Cloud Run-time scan
Tenable.cs will scan the cloud in run-time (CSPM) and report the findings.  This may take up to 2-3 minutes.

1.  On AWS, Cloud Run-time Scan configuration  
    a.  Configure and **Run the default cloud scan**
    b.  When complete, refresh <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/refresh.png" height="45" alt="refresh" />
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
a.  Upon completion of scan, be sure to *refresh* <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/refresh.png" height="45" alt="refresh" />
the screen to displaly the results after the cloud scan is completed.   
b.  After refresh, how many ***Drifts*** were found?

</p>