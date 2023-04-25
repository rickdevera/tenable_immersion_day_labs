# Lab Exercise 01
## Onboarding

### Task Summary:

- Able to log in and navigate around the Tenable Cloud Security dashboard
- Able to create a Tenable Cloud Security project(s)
- Able to identify policies assigned to a project.
- Able to create and store API keys into AWS Secrets Manager
- Able to run a Cloud Formation Template



### Prerequisites
-  Skills:
    - [ ] Prior knowledge of AWS Dashboard
	- [ ] Basic Knowledge for Cloud Formation Stacks
    - [ ] Prior knowledge of networking, Remote Desktop Connection to Microsoft Windows.  
    Note:  If not using local laptop.

### Resources
- Tenable account (assigned by instructor)
- Access to https://cloud.tenable.com/
- Access to Tenable Documentation https://docs.tenable.com/Tenablecs.htm
- Credentials to Bastion Host and Windows Desktop are in the Output Properties

____
**Documentation Notes:**  

- Tenable.cs is used interchangeably with Tenable Cloud Security.  
- Tenable.io is used interchangeably with Tenable Vulnerability Management

____

### Tasks


#### Needed if running Lab06.  Skip to the next Section

1. Remote Desktop Protocol (RDP) – use Remote Desktop connection to login into the external IP using your preferred client (i.e. Microsoft Remote Desktop)

    1.  You will need to navigate to the sign-in page

        1. Use the Google Chrome to navigate to Tenable sign-in page. 
	        - There's bookmark in Chrome or shortcut on the Bastion host's Windows Desktop 
    	    - Use Tenable.cs credentials assigned by the class instructor.
        2. You're in *Tenable.io Workspace* page
        3. `Click` the icon to open **Tenable.cs**

##### Create a Project
**A Project** is a group of any combination of connections, policies, cloud accounts:

1.  From the Tenable Cloud Security dashboard, click on the (+) button on the top-left menu,
1.  `Click` on **Create a Project**,
1.  Provide a ***Project Name*** (ie. **Lab01-Project**), then click ***Continue***,
1.  `Choose` **AWS** as the provider.

##### Verify the Assigned Policies
This dialog box will provide the Project UUID and the properties for the project.

From the Tenable Cloud Security Dashboard
1.  `Click` on the **Projects and Connections** tab,
1.  `Click` on the Project you created,
1.  On the pop-up, look for the Active Policy Group,
1. `Click` on the ***pencil*** icon.
1.  `Deselect` the current selections,
1.  `Search` for **NIST** and select the **Policy** groups for <u>**AWS**</u>.  (i.e. NIST-800-53 and NIST-800-171),
1.  `Save` your selection.


####  QUESTION

1.  What is the *Project ID* ?  
- Each project has a ID associated with a project.
- Project ID is also used to initiate scans at the CLI.  
.  What are the other properties to the Project?Can you exclude resources from scans?

#### END OF LAB

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)
