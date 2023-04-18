# Lab Exercise 01
## Onboarding

### Objective:

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

### Resources
- Tenable account (assigned by instructor)
- Credentials to Bastion Host and Windows Desktop are in the Output Properties

### Tasks


#### Needed if running Lab06.  Skip to the next Section
There are two methods for remote access. 

1. Remote Desktop Protocol (RDP) – use Remote Desktop connection to login into the external IP using your preferred client (i.e. Microsoft Remote Desktop)

    1.  You will need to navigate to the sign-in page

        1. Use the Google Chrome to navigate to Tenable sign-in page. 
	        - There's bookmark in Chrome or shortcut on the Bastion host's Windows Desktop 
    	    - Use Tenable.cs credentials assigned by the class instructor.
        2. You're in *Tenable.io Workspace* page
        3. `Click` the icon to open **Tenable.cs**

<!--#
#####  Create an API key 

The API key is used as an authetication key to verify validation questions using Tenable's REST API.  More information in using Tenable API keys can be found at https://developer.tenable.com/ (Search for the Cloud Security section for API examples)

1.  From Tenable Cloud Security dashbord, `Click`on the **Integrations** icon from the left menu,
1.  `Click` on **API Tokens**,
1.  `Click` on the ***Click to generate an API Token,
1.  The new token will be added to the bottom of the list.  `Click` on the <u>copy</u> icon to `Save` the token to the clipboard.  

##### Store API key 
A cloud formation template will be used to store the API key in secrets manager.

1.  Navigate to AWS Console,
1.  Select the **CloudFormation** service,
1.  Click on **Create Stack->with New resources (standard)**,
	  - Select **Template is Ready** ,
    - Select **Amazon S3 URL**,
    - From **Output Properties**, `Copy` the link from the parameters,<u>**StoreAPI**</u>.
1.	Click on **Next**,
1.  In the window **Specify stack details:  
    1.  Enter the Stack name:  <u>**TenableStoreAPIkey**</u>,
    1.  Enter the **ApiKey** (found in the steps above),
    (ie Copy the key from **TenableCS Dashboard->Integrations->Create API Key**),
1.  `Click` **Next**,
1.  `Click` **Next**,
1.  `Click` **Submit**,
1.  `Click` the refresh button to verify the status **CREATE_COMPLETE**.
-->

##### Create a Project
**A Project** is a group of any combination of connections, policies, cloud accounts:
1.  From the Tenable Cloud Security dashboard, click on the (+) button on the top-left menu  ,
1.  `Click` on **Create a Project**,
1.  Provide a ***Project Name*** (ie. **Lab01-Project**), then click ***Continue***,
1.  `Choose` **AWS** as the provider.

##### Verify the Assigned Policies
This dialog box will provide the Project UUId and the properties for the project.

From the Tenable Cloud Security Dashboard
1.  `Click` on the **Projects and Connections** tab,
1.  `Click` on the Project you created	,
1.  On the pop-up, look for the Active Policy Group,
1. `Click` on the ***pencil*** icon.
1.  `Deselect` the current selections,
1.  `Search` for **NIST** and select the **Policy** groups for <u>**AWS**</u>.  (ie NIST-800-53 and NIST-800-171),
1.  `Save` your selection,


#### VALIDATION QUESTION

1.  What is the *Project ID* (UUID) for the project (Lab01-Project) created in this lesson?

#### END OF LAB

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)
