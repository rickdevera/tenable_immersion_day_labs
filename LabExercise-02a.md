# Lab Exercise 02

## IaC Scanning

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

##### Integrate Repository (GitHub)

The steps in this lab will use **Code repositories** to scan.
Each step has sample source code needed from a repository

##### Onboard GitHub Account

1.  Log into GitHub using your personal account or the credential you used to create in task 1
2.  Go to Task 1 repository link above.
3.  Click on **Fork->Create a new fork** button <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/github_create_fork.png" height="150" alt="fork" />
4.  Follow directions in Github  
a.  Expand the **tenable-awsjam-cft-demo** repository.  
b.  Select the **awsjam** branch  
c.  Select the **cft** sub-directory  

##### Adding Repository to Project

1.  On Tenable.cs, click on the question mark <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/question_mark_getting_started.png" height="50" alt="gettting started" /> on the top right side of the dashboard browser.
2.  Click **Getting Started with Tenable.cs ->Add Repositories**
3.  Step through the wizard
4.  Select **Version Control**, click **Continue**
5.  Under <u>Connect to a version control provider</u>  
  a.  Select **GitHub -> Connect**  
  b.  Click **Continue**
6.  Select a repository for each project.  
  a.  Repeat the above steps for each project OR  
  b.  Select Onboard all repositories, which will assign a <u>Default Github Repository</u>, this can be modified by by editing the Project)   
  
**Quick Reference:**  https://docs.tenable.com/tenablecs/Content/GettingStarted/ConnectingRepositories.htm


#### Scan IaC

Reference:  https://docs.tenable.com/tenablecs/Content/GettingStarted/IaCScans.htm

1.  On the Tenable.cs Dashboard, click on PROJECTS & CONNECTIONS   
2.  Hover over **Run Scan** and click **IaC Scan**

#### View Findings/Misconfigurations

1.  On the Tenable.cs Dashboard, click on Findings from the left panel

####  Create Pull Requests 

1.  Select the *Failing Policy*. (Example:  <u>***Ensure Security Groups do not have unrestricted specific ports open - (SSH,22))***</u>
2.  Click on the three-dots <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/three-dot-button.png" height="80" />
3.  Select Create a pull request.
**Reference:**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/CreatePullRequest.htm

##### Setup Auto Remediation

**Reference**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/Auto-Remediation.htm?Highlight=pull%20requests   

##### Display all Pull Requests

1.  In Tenable.cs, select **Remediate** on the left menu
2.  Select Fix PRs. (Remediate -> Fix PRs)

