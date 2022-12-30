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

### Onboard GitHub Account

#### Create GitHub account

1. Navigate to GitHub <a href="http://github.com" target="_blank" rel="nofollow noopener noreferrer">github.com</a>
1. On the right top, click Signup to create a GitHub account
1. Fill the information, and validate your email address

1.  Log into GitHub created from **LabExercise-01** and use this account to create a new fork from your personal account or use the credentials used to create the GitHub account in  **LabExercise-01**
1.  Go to  repository link above.
1.  Create a new fork from https://github.com/RDev-TechAlliance/tenable-awsjam-demo.git 

1.  Follow directions in Github
    1. Expand the **tenable-awsjam-demo** repository
    1. Select the **awsjam** branch  

### Adding Repository to Project

1.  On Tenable.cs, on the left menu bar, click on the (+)
1.  Click on ***Connection->Repository***
1.  Select **Version Control**, click **Continue**
1.  Under <u>Connect to a version control provider</u>  
  1.  Select **GitHub -> Connect** 
  1.  If you have not logged in, enter the username and password of the GitHub account
  1.  Click **Continue**
1.  Select  all repositories listed.  Some of these repositories will be used in other labs.


  
**Quick Reference:**  https://docs.tenable.com/tenablecs/Content/GettingStarted/ConnectingRepositories.htm


### Scan IaC

Reference:  https://docs.tenable.com/tenablecs/Content/GettingStarted/IaCScans.htm

1.  On the Tenable.cs Dashboard, click on PROJECTS & CONNECTIONS   
2.  Hover over **Run Scan** and click **IaC Scan**
3.  

#### View Findings/Misconfigurations

1.  On the Tenable.cs Dashboard, click on Findings from the left panel

####  Create Pull Requests 

1.  Select the *Failing Policy*. (Example:  <u>***Ensure Security Groups do not have unrestricted specific ports open - (SSH,22))***</u>
2.  Click on the vertical ellipses menu 
3.  Select Create a pull request.
**Reference:**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/CreatePullRequest.htm

##### Setup Auto Remediation

**Reference**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/Auto-Remediation.htm?Highlight=pull%20requests   

##### Display all Pull Requests

1.  In Tenable.cs, select **Remediate** on the left menu
2.  Select Fix PRs. (Remediate -> Fix PRs)

