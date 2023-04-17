# Lab Exercise 03

## Cloud Scanning (CSPM) and Cloud Drift Detection



####Task Summary
1.  Create a cloud connection beteween AWS account and Tenable Cloud Security
1.  Create a new project for cloud scans
1.  Creater an AWS IAM role and policy using cloud formation templates
1.  Execute a real-time (cloud) scan
1.  Idenitfy Configuration Drift

____
**Documentation Notes:**
- Tenable.cs is used interchangeably with Tenable Cloud Security
- Tenable.io is used interchangeably with Tenable Vulnerability Management
_____

### Prerequisites
- Familiar with Tenable Cloud Security Dashboard 
- Familiar with AWS Cloud Networking concepts
- Familiar with AWS Cloud Formation Templates
- Familiar with AWS IAM Roles and Policies

### Tasks


#### Setup IAM Permission
##### Download YAML 
1.  Search for IAMroles in the Output Properties and copy the S3 URL link address

##### Create and run the Cloud Formation stack
<sup>Note:  Use the parameter, **ExternalId** found in *Output Properties*.

1.  Navigate to AWS Console,
1.  Select the **CloudFormation** service,
1.  Click on **Create Stack->with New resources (standard)**,
	  - Select **Template is Ready** ,
    - Select **Amazon S3 URL**,
    - Enter S3 URL link from Output Properities,
1.	Click on **Next**,
1.  In the window **Specify stack details:  ,
    1.  Enter the Stack name:  <u>**tenable-awsjams-role**</u>,
    1.  Enter the **External Id** (exter),
    1.  AllowVulnerabilityScanning should be set to **True** and will be used in a future lab to scan EC2 instances,
1.  Click **Next**,
1.  *Accept* ***Acknowledgement*** and Click **Submit**.

    
1.  When completed, you will use the ARN and ExternalId Values to connect Tenable to AWS  

#### Create a cloud connection on Tenable Cloud Security


1.  On Tenable Cloud Security, create an AWS connection,
1.  From the Tenable Cloud Security dashboard, goto the the left menu and click on the (+) symbol,
1.  Click on *Connection->AWS connection*,
1.  Select Onboard AWS account, and click **Continue**,
1.  Choose **Public cloud** and click **Continue**,
1.  Enter the **Read Only Role ARN** form the values saved above,
1.  Enter the **External ID**, click on **Continue**,
1.  *Create or Select* the **security_group_scan** project,
    1.  If the project is not defined, click on **Add a project**,
    1.  Enter **Lab03-Project**  ,
    1.  Click on the *check box* to select the project,
1.  Click on **CONNECT CLOUD ACCOUNT**.

#### Create a Scan Profile

1.  From the Tenable Cloud Security dashboard, select the **PROJECTS & CONNECTIONS** tab,
1.  `Click` on the *ellipse* button on the right of the project and `select` **Manage cloud scan profile**,
1.  `Click` on the *ellipse* button and `select ` **Duplicate*,
1.  Change the default scan to the new profile,
    - `Click` on the **ellipse** and `select` **<u>Use as default scan**</u>,
1.  `Click` on **Edit**,
1.  Clear all selections in *Step 1 - Cloud config assessment options*,
    - `Click ` on **Select all**,
    - `Click` on **Clear all**,
1.  `Expand` the drop down for **Security, Identify, and Compliance**,
    - `Select`  **Security Group**,
1.  At the top, `click` on the name to rename the **Scan Profile name** to **<u>Lab03-Profile</u>**,
1.  `Click` the **Save** button.


##### Perform AWS Cloud Run-time scan
1.  From the dashboard, search for **Active Policy groups** -`Click` on the *pencil* icon to change the policy groups,
1.  `Deselect` the current selections,
1.  `Search` for **NIST** and select the **Policy** groups for <u>**AWS**</u>.  (ie NIST-800-53 and NIST-800-171),
1.  `Save` your selection,
1.  From the **PROJECTS & CONNECTIONS** dashboard:  
    - `Select` the *ellipse*,
    - **Set Baseline**,
    - `Run` the cloud scan.


##### Verify Misconfiguration
1.  When completed scan, `Click` on **Findings** from the left menu,
1.  `Select` Misconfigurations from the top menu,
These are names of all the ***Policies* found misconfigured,
1.  `Click` on **Filters->Projects** and select the name of the project that was created (ie Lab03),
1.  In the Search box, type in **SSH**,
1.  Select the Policy for **HIGH** severity. <sup>(denoted by Red H)</sup>,
1.  This is the <u>**Policy name**</u> for the misconfigured resource,
1.  `Click` on the **Policy name**,
1.  To ignore additional resources:  
    1.  `Click` on the checkbox for all resources that <u>***DOES NOTE contain***</u> the string **AWSInternalSecurityGroup**,  
    - **Reason**:  *Not applicable*,
    - **Ignore for**:  *Forever*,
    - **Comments**:  *AWSJAMS*.


### Remediate Misconfigured Security Group
1.  One the AWS Console:  
    1.  Use the <u>Security Group ID</u> for **AwsInternalSecurityGroup** found in *Output Properties*,
    1.  Using the **AWS Console**, goto the **VPC Dashboard->Security Groups**,
    1.  In the *Search/Filter* box, paste the <u>Security Group ID</u>,
    1.  Select the *Security Group* and Select **Action->Edit Inbound rules**,  
    1.  Modify the ***SSH*** rule that contains  a the Source IP ( 0.0.0.0/0) to (10.1.1.0/24).
  c.  Save the Rules.

### Drift Detection

1.  Rescan the project (ie **Lab03-project**).



**Note:** the changed values in 
<u>Misconfigurations</u> and <u>Drift</u>




## VALIDATION QUESTION

1.  Enter the Security Group Id found in Output Properties.



## END OF LAB</sup>
## END OF LAB

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)