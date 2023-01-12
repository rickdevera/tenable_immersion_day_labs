# Lab Exercise 01
## Onboarding

### Objective:

- I can access the bastion host (jumpbox) remotely to access Tenable and AWS.
- I can log into Tenable.io and navigate around the Tenable.cs dashboard
- I can create a Tenable.cs project(s)
- I can identify policies assigned #to a project.



### Prerequisites
-  Skills:
    - [ ] Prior knowledge of GitHub - https://docs.github.com/en/get-started/quickstart/hello-world
    - [ ] Prior knowledge of networking, and Microsoft Windows and browser

### Resources
- Tenable.io account (assigned by instructor)
- Credentials to Bastion Host and Windows Desktop are in the Output Properties

### Tasks

#### Navigate to the environment
There are two methods for remote access. 

1. Browser based (Guacamole) - login to the public ip: http://[GuacamolePublicIP]:8080/guacamole
        - Use this method if your desktop does not have access to an RDP client.  
        - Sign in and select Windows Desktop

2. Remote Desktop Protocol (RDP) – use Remote Desktop connection to login into the external IP using your preferred client (i.e. Microsoft Remote Desktop)

    1.  You will need to navigate to the sign-in page

        1. Use the Google Chrome to navigate to Tenable sign-in page. 
	        - There's bookmark in Chrome or shortcut on the Bastion host's Windows Desktop 
    	    - Use Tenable.cs credentials assigned by the class instructor.
        2. You're in *Tenable.io Workspace* page
        3. `Click` the icon to open **Tenable.cs**

##### Create a Project
**A Project** is a group of any combination of connections, policies, cloud accounts:
1.  From the Tenable.cs dashboard, click on the (+) button on the top-left menu  
1.  `Click` on **Create a Project**
1.  Provide a ***Project Name*** (ie. **Lab01-Project**), then click ***Continue***
1.  `Choose` **AWS** as the provider

#### Retrieve the Policies
From the Tenable Cloud Security Dashboard
- `Click` on the **Projects and Connections** tab
- `Click` on the Project you created	
- On the pop-up, look for the Active Policy Group
- `Click` on the ***pencil*** icon


### VALIDATION QUESTION

1.  What are the default policies associated with a New Project?

## END OF LAB

[[[Return to Wiki Home Page|Home]]](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)
