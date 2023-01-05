# Lab Exercise 04

## Scanning for Vulnerabilities


### Objective:

- I can create EBS snapshots
- I can Setup Scan Profiles for Agentless Assessment
- I can verify vulnerabities for EC2 instances

### Prerequisites


### Tasks

#### 1.  Preparation

1.  On the AWS console
    1.  Go to the **EC2 Dashboard**, validate Instance Name **AA_EC2_Demo**  exists
    1.  Go to **Elastic Block Store->Snapshot**  
    1.  Click on **Create snapshot**  
  d.  Click on the **Instance** radio button      
  e.  Click on the ***Instance ID*** dropdown menu, search for **AA_EC2_Demo** 
  f.  Select the Instance for **AA_EC2_Demo**
  g.  Enter a description:  **Agentless Demo EC2 Snapshot**   
  h.  Click on **Create snapshot**    
    This may take a few menutes   
  g.  Click the refresh button and **WAIT** for the <u>Snapshot Status</u> to display status as **Completed**.  


#### Setup a Project 
1.  In Tenable.cs, create a project  
    1.  Click on the (+) button on the left menu  
    1.  Enter the project name: **AA_demo**  
    1.  Select **AWS**  
    1.  Click on **Create**

#### Scan the project

This will scan the snapshot of the EC2 instance


1.  From the Tenable.cs Dashboard, Click on **PROJECTS & CONNECTIONS** tab
1.  Click on the **Projects** icon.
1.  Click on the **AA_demo** project.
1.  Click on the *pencil* icon for <u>Cloud accounts</u>
1.  Enable the *cloud account* (created from LabExercise-03a)
1.  Click the **Save** button 

1.  On the main dashboard, create a scan profile for **AA_demo**.  
    1.  For the project **AA_demo**, click on **Run Scan->Cloud Scan->Manage Scan Profiles**.    
    1.  Click on **New Scan Profile** button.  
    1.  Enter an <u>Scan Profile name:</u>  **AA_profile_demo**  
    1.  Search for EC2 Instance, and *click* the <u>check-box</u> for EC2 Instance.
    1.  Scroll down to <u>Step 2</u> and turn on **Enable Vulnerability Scan**
    1.  *Click* on the **Preview** button to verify the profile configuration.
    1.  *Click* on **Create Scan Profile** button
    1.  *Click* on  the vertical ellipses for the profile just created and select **Use as default scan**

1.  Scan for vulnerabilities
    1.  *Click* on **Run scan->Cloud scan->Run default scan profile**
    1.  Depending on the size and how many vulnerability scan are in progress, this may take several minutes to complete.
    1.  *Refresh* the main dashboard display
### View vulnerabilties
1.  From the main dashboard, click on the **Vulnerabilties** tab.
1.  Note the vulnerabilties associated with this instance.

### View from Tenable.io Dashboard

1.  Goto http://cloud.tanble.com
1.  Select top-left pulldown **Explore->Findings**
1.  *Click* on the **funnel icon**
1.  *Click* on **Select Filters**
1.  *Search* for **Scan Origin** and *Enable* the **check-box**
1.  *Exit* the dialog box
1.  *Scroll* down to the **Scan Origin** section and *enable* the *checkbox* for **Agentless Assessment**
1.  *Click* **Apply**

### Search for Asset

1.  Find the <u>Instance ID</u> for a scanned EC2 instance
1.  From **Explore->Findings** display, *enter* the *Instance ID* in the search field.
1.  Verify Vulnerable Plug-ins found.

## VALIDATION QUESTION

1.  Will AA scan for instances without a snapshot?

## End of Lab 

[Return to README](https://github.com/rickdevera/tenable_immersion_day/blob/main/README.md)