# Lab Exercise 01
## Onboarding

### Objective:

- I can access the bastion host (jumpbox) remotely to access Tenable and AWS.
- I can log into Tenable.io and navigate around the Tenable.cs dashboard
- I can create a Tenable.cs project(s)
- I can assign new policies to a project.
- I can create a GitHub account


### Prerequisites
- Tenable.io account
- Prior knowledge of GitHub - https://docs.github.com/en/get-started/quickstart/hello-world
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser

### Tasks

#### To navigate to the environment
There are two methods for remote access. Bastion Host credential is in the **Inventory** Section

a. Browser based (Guacamole) - login to the public ip: http://[GuacamolePublicIP]:8080/guacamole

b. Remote Desktop Protocol (RDP) – use Remote Desktop connection to login into the external IP using your preferred client (i.e. Microsoft Remote Desktop)

You will need to navigate to the right page
1. Use the Google Chrome to navigate to Tenable sign-in page. 
	- There's bookmark in Chrome or shortcut on the Bastion host's Windows Desktop 
	- Use Tenable.cs credentials found in **Output Properties** to sign in
2. You're in Vulnerability Management Overview page
3. Using the drop down from the left top corner, scroll down and click to open **Cloud Security**

##### Create a Project
**A Project** is a group of any combination of connections, policies, cloud accounts:
1.  From the Tenable.cs dashboard, click on the <img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/left_menu_plus.png" height="50" /> button on the top-left menu  
2.  Click on Project
	1. Provide a Name, then Continue
	2. Choose AWS as the provider, then CREATE

Alternatively, use the Getting Started Guide
1.  From the Tenable.cs dashboard, click on the question mark icon<img src="https://aws-jam-challenge-resources.s3.amazonaws.com/scan-and-remediate-ninja/question_mark_getting_started.png" height="50" />
2.  Click **Getting Started with Tenable.cs-> Add Project**
3.  Click on Project
	1. Provide a Name, then Continue
	2. Choose AWS as the provider, then CREATE

#### Retrieve the Policies
From the Tenable Cloud Security Dashboard
- Click on the **Projects and Connections** tab
- Click on the Project you created	
- On the pop-up, look for the Active Policy Group
- Click on the ***pencil*** icon
- Look for the 2 policies with boxes checked

##### Create GitHub account

1. Navigate to GitHub <a href="http://github.com" target="_blank" rel="nofollow noopener noreferrer">github.com</a>
2. On the right top, click Signup to create a GitHub account
3. Fill the information, and validate your email address

##### Validation Question
1.  What are the default policies associated with a New Project.

##### **Extra Credit** Adding an Industry Standard Compliance Policy
1.  Create a new policy and assign ONLY <u>NIST 800-53 Best Practices for AWS</u> in the current policies