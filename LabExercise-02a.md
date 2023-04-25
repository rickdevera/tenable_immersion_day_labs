# Lab Exercise 02

## IaC Scanning

### Task Summmary:

- Create a GitHub account
- Create a GitHub connection
- Assign a repository to a Tenable.cs project
- Fork a GitHub repository
- Scan IaC
- Identify Misconfigurations
- Remediate code and create Pull Requests
- Setup Auto Remediation

### Prerequisites
- Tenable.io account
- Prior knowledge of GitHub (Please read- https://docs.github.com/en/get-started/quickstart/hello-world)
- Understand use cases of Infrastructure as Code (IaC)
- Completed LabExercise-01.

## Tasks

### Integrate Repository (GitHub)

The steps in this lab will use **Code repositories** to scan.
Each step has sample source code needed from a repository

###  Working with GitHub Account

#### Create GitHub account

If this has already been done, skip to the next section

1. Navigate to GitHub <a href="http://github.com" target="_blank" rel="nofollow noopener noreferrer">github.com</a>
1. On the right top, click Signup to create a GitHub account
1. Fill the information, and validate your email address

#### Fork a Github repository

1.  From your GitHub account, create a new fork from https://github.com/RDev-TechAlliance/tenable-awsjam-demo.git.

1.  Verify forked repository exists in your account.

### Scan files

#### Create a Project

1.  Create a new project
    - Name:  Lab02
    - Provider: AWS

### Adding Repository to Project

1.  In Tenable.cs, on the left menu bar, click on the (+)
1.  Click on ***Connection->Repository***
1.  Select **Version Control**, click **Continue**
1.  Under <u>Connect to a version control provider</u>  
  1.  Select **GitHub -> Connect** 
  1.  If you have not logged in, enter the username and password of the GitHub account
  1.  Click **Continue**
1.  Select the repository **tenable-awsjam-demo**
Some repositories may be listed and can be selected, however they will not be used in this lab.
1.  `Select` **Continue**
1.  `Assign` (enable) **Lab02** <sub>(or projected created for this lab)</sub>
1.  `Select` **Connect*


**Quick Reference:**  https://docs.tenable.com/tenablecs/Content/GettingStarted/ConnectingRepositories.htm


### Scan IaC

Reference:  https://docs.tenable.com/tenablecs/Content/GettingStarted/IaCScans.htm

1.  On the Tenable.cs Dashboard, click on PROJECTS & CONNECTIONS   
2.  Hover over **Run Scan** and *Click* **IaC Scan**

#### View Findings/Misconfigurations

1.  On the Tenable.cs Dashboard, *Click* on **Findings** from the left panel
1.  Select the Misconfigurations tab

####  Create Pull Requests 

1.  Select the *Misconfigurations*.
1.  Enter **SSH**, in the **Search Bar**.
    1.  Verify the scan found a *misconfiguration* - <u>***Ensure Security Groups do not have unrestricted specific ports open - (SSH,22))***</u>
1.  Click on  <u>***Ensure Security Groups do not have unrestricted specific ports open - (SSH,22))***</u>
1.  Click on the vertical ellipses menu (right side)
1.  Select Create a pull request.
1.  In the text block **Secure Value**, enter a valid IP (***10.1.0.99/24 ***)  
1.  Under **Branch**, Select the **AWSJAM** branch 
1.  Click on the ***Preview*** button to verify the changes.
1.  Click on ***Create PR**


**Reference:**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/CreatePullRequest.htm

####  Verify Remediation 

1.  Log into your GitHub account
1.  Go to the repository ***tenable-awsjam-demo***
1.  Click on the **Pull Request** tab
1.  Verify changes, `click` on the **Files changed**
    1.  Note: changes from red to green
1.  Click on ***Merge Pull Request*, to submit the changes
1.  `Verify`  the changes have been made.


####  Verify Changes

1.  In Tenable.cs dashboard, Select the Project created in the section above and run an IaC scan
1.  Verify the Misconfigured resource is no longer displayed.


**Reference**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/Auto-Remediation.htm?Highlight=pull%20requests   


### VALIDATION QUESTION

1.  What are two ways I can verify status of a pull request?
2.  Is there a way to integrate pull request with a ticketing system? 



## END OF LAB

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)