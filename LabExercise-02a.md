# Lab Exercise 02

## IaC Scanning

### Objective:

- I can create a Github account
- I can create a Github connection
- I can assign repositories to a Tenable.cs project
- I can fork a Github repository
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
    - Name:   Lab02-Project
    - Provider:  AWS

### Adding Repository to Project

1.  On Tenable.cs, on the left menu bar, click on the (+)
1.  Click on ***Connection->Repository***
1.  Select **Version Control**, click **Continue**
1.  Under <u>Connect to a version control provider</u>  
  1.  Select **GitHub -> Connect** 
  1.  If you have not logged in, enter the username and password of the GitHub account
  1.  Click **Continue**
1.  Select the repository **tenable-awsjam-demo**
Some repositories may be listed and can be selected, however they will not be used in this lab.


**Quick Reference:**  https://docs.tenable.com/tenablecs/Content/GettingStarted/ConnectingRepositories.htm


### Scan IaC

Reference:  https://docs.tenable.com/tenablecs/Content/GettingStarted/IaCScans.htm

1.  On the Tenable.cs Dashboard, click on PROJECTS & CONNECTIONS   
2.  Hover over **Run Scan** and click **IaC Scan**
3.  

#### View Findings/Misconfigurations

1.  On the Tenable.cs Dashboard, click on Findings from the left panel
1.  Select the Misconfigurations tab

####  Create Pull Requests 

1.  Select the *Misconfigurations*. <u>***Ensure Security Groups do not have unrestricted specific ports open - (SSH,22))***</u>
1.  Click on the vertical ellipses menu
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
1.  Verify files changed
1.  Click on ***Merge Pull Request*, to submit the changes


####  Verify Changes

1.  Select the Project created in the section above and run an IaC scan
1.  Verify the Misconfigured resource is no longer displayed.
1.  In Tenable.cs, select **Remediate** on the left menu
1.  Select Fix PRs. (Remediate -> Fix PRs)
### Optional:  Setup Auto Remediation

**Reference**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/Auto-Remediation.htm?Highlight=pull%20requests   


### VALIDATION QUESTION

1.  What are two ways I can verify status of a pull request?
2.  Is there a way to integrate pull request with a ticketing system? 




