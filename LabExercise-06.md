# Lab Exercise 06

## Using Visual Studio Code (VS Code) and Tenable.cs command-Line tools

### Objective:

- I can run 
- I can Create a Custom Policy Group
- I can Add Custom Policy Group to Project
- I can Scan custom policy  

### Prerequisites
- Tenable.io account
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser
- Windows Desktop
- Completed Labs 1 and 2

### Tasks

Open terminal
Run the 
  ____


1.  Login to the Windows Desktop using the credentials supplied in Output Properities

### Create OAUTH credentials

1.  At the Windows Command Prompt, *type in the command* `cmdkey /list`
1.  If the Windows credential name:  **vscodevscode.github-authentication/github.auuth* is listed, delete the credential.
    1.  Run the command `cmdkey /delete:vscodevscode.github-authentication/github.auth`
    1.  Run the command `cmdkey /list` to verify the credential has been removed.


### Setup VS code

1.  `Click` on the **Visual Studio Code** icon
1.  `Click` on **Clone Git Repository**'
1.  On the top-middle of the menu bar, `click` on **Clone from GitHub**
1.  Visual Code popup dialog should appear requesting to sign-in to GitHub.  `Click` **Allow**
1.  `Enter` your credentials for Github
1.  Upon successsful authentication, `Open` Visual Studio Code
1.  Visual Studio Code my request to *Allow an extension to open this URI*, `click` **Open** to continue
1.  A list of repositories will be displayed on the top-middle menubar.
    1.  `Select` **tenable-awsjam-demo**.
    1.  Store the file in the **PROJECTS** folder
    1.  `Click` **Open**

The a copy of the repository is now on the local computer.

### Run the IaC scan (standalone)

1.  In VS Code, `Right` click on **main.tf**
    1.  `Select` **Tenable.cs Scan**
    1.  `Select` **terraform** from the pulldown menu
1.  Note the details in the **OUTPUT** console window in the VS Code 

## VALIDATION QUESTION

1.  From the **Output** windows:
    1.  How many *violated policies* (misconfigured)?
    1.  How many found with *High Severity*?



### Configure VS Code (Integrated Mode)
 
1.  On the right menu of VS Code, `click` the **Extensions** icon and `select` Tenable.cs.

1.  Follow the <u>steps</u> for **Integrated Mode (Commercial)**
  1.  *Note:* You will use the project created in Lab 02.  **
1.  When completed, right-click on **main.tf**, and `select` **Tenable.cs Scan->init**, `press` enter for defaults
    - This will initialize the backend and plug ins
1.  `Right-click` on **main.tf** and `select` **plan**
1.  When completed, `click` on the **Output** tab in the *Console* window.
    1.   Note:  The details in the output.
    1.  `Scroll` down and `Click` on the link preceded by *Please visit.. for further analysis*

## VALIDATION QUESTION

1.  Are the results the same for *high* severity violations?


### Download Tenable.cs CLI

1.  On the Tenable.cs dashboard, `select` the project **tenable_awsjam_demo** from the **PROJECTS & CONNECTIONS** tab.
1.  Select **CLI**_On the console window, `click` on **TERMINAL**
1.  From the Project Details window, `click` on **CLI**.
    1.  Download the CLI for *Windows OS*
    1.  Copy the CLI into the target folder of the IaC repository (repository cloned from VS Code)


### Run from the command-line

1.  Go back to the console window from VS Code
1.  `Select` **Terminal**
1.  Verify the configuration file that was unzipped in an earlier step when *Configuring Integrated mode* (ie config/config_tenable-awsjam-demo)
1.  Run `./accurics plan -config=config\config_tenable-awsjam-demo`
1.  Using the *Chrome* browser,  open the file **accurics_report.html** found in the local repository folder.


## VALIDATION

1.  What other file types can be scanned using the CLI?


## END of LAB




1.  If a credential name, 
1.  From the browser, connect to the Tenable.cs dashboard.  
1.  From the Tenable.cs dashboard, `Select ` the **PROJECTS & CONNECTIONS** tab
1.  `Click` on the **iac_demo_project** project.
1.  `Click` on **CLI**
1.  Follow the instructions for downloading the CLI

Pre Requisites

For Integrated mode scans, you must have the following:

A Tenable.cs user account with an Operator or greater role.
A project in the Tenable.cs console to scan your IaC repository. You can use this project to create the CI/CD builds.
Steps

In the VS Code workspace, select the Tenable.cs extension.
Click View > Command Palette.
The Command Palette box appears.
Select Tenable.cs Mode and then select Integrated.
Access Tenable.cs from https://cloud.tenable.com/.
The Tenable.cs Dashboard page appears.
On the Home page, click the Projects and Connections tab.
Click your project to view its details.
In the upper-right, click the Configuration link to download the configuration .zip file and extract it to a local folder.
In the VS Code workspace, click View > Command Palette.
From the Command Palette box, choose Tenable.cs Configuration and select the configuration file that you saved in step 7.
Right-click any IaC file or directory and click Tenable.cs Scan.
The Tenable.cs extension displays a list of scan commands.
Select the required command from the displayed scan commands.
(Optional) Provide the required command options for the selected command:
Commands init, plan, and workspace take parameters equivalent to Terraform CLI.
Commands tgplan, tgplanall, and plan-all take parameters equivalent to Terragrunt CLI.
The Tenable.cs extension performs the scan and reports the results in output window as well as in the Tenable.cs console.

For more information, see Tenable.cs documentation.

Configuration settings
Tenable.cs extension provides two scopes for settings:

User: Settings that apply globally to any instance of VS Code. You must update these settings manually.
Workspace: Settings that apply to only the workspace that is open. The Workspace settings are automatically set when you run the Tenable.cs Configuration operation.
If you specify both User and Workspace settings, the Workspace settings take precedence.

To modify the User settings:

Click Tenable.cs on the status bar or click File > Preferences > Settings.
The Settings editor appears.
In the User tab, update the following fields:
API token: Authentication token (only for integrated mode)
App URL: Repository URL (only for integrated mode)
Project ID: ID of the project in the Tenable.cs console (only for integrated mode)
Scan Mode: Standalone or Integrated

#### Create a Project

  1.  On the Tenable.cs Dashboard, create a new project - **custom_policy_project**
  1.  `Select` the provider **AWS**
  1.  `Click` on the project **custom_policy_project**
  1.  `Click` on the **Repositories** *pencil* icon
  1.  `Select` the repository create from the prior labs (eg.  *tenable-awsjam-demo.git*)
  1.  `Save` the configuration


#### Compliance Report Dashboard


  1.  On Tenable.cs Dashboard left menu, `click` the icon for Reports 
  1.  Under the *Projects* filter, `select` the project **custom_policy_project**</u>
  1.  `Select` **Filters**
      1.  `Enable` filter on 
          - Policy Status:  **Non-Compliant**
          - Severity:  **High**
  1.  `Expand` the control *Security Group*
  1.  `Click` **APPLY**
  1.  `Expand` **Infrastructure Security**
  
  ## VALIDATION QUESTION
  1.  What is the compliance coverage for Infrastructure Security?
  1.  HOw many High severity, non-compliant policies were found?
  1.  What is the compliance coverage for the Project we selected?



  ### Create a Custom Policy Group

1.  On the Tenable.cs dashboard, *Create* a new **Custom Policy**
    1.  `Click` on the left menu (+) and select **Custom Policy**
    1.  `Select` **Add Policy Group**
    1.  Filter on the following:
        1.  Severity: High
        1.  Provider:  AWS
        1.  Category:  Infrastructure Security
    1.  `Enable` **ALL** policies
    1.  `Select` **Continue**
    1.  `Type` in the Policy Group Name: **custom_Infrastructure_Security_policy_group**
    1.  `Select` **AWS**
    1.  `Select` **Enforce**
    1.  `Select` the **DONE** button to complete group creation.

## VALIDATION QUESTION
1.  Can you create a custom policy group that contains a subset of policies from each Benchmark?

### Assign Custom Policy to Project

1.  On Tenable.cs dashboard, `click` on the project
1.  `Click` on pencil icon for *Active policy groups*
1.  `Deactive/disable` the current policy group selections
1.  `Search`  for **custom_Infrastructure**
1.  `Enable` **custom_Infrastructure_Security_policy_group**
1.  `Click` **SAVE**
1.  `Verify` *Active policy groups* updated with new custom policy
1.  `Click` on **Run scan->IaC scan** for the <u>custom_policy_project</u>

## VALIDATION QUESTION

1.  Can custom policy group be created to build a customized policy that contains policies from each Industry Benchmark?

### Optional Challenge Task - Remediate Misconfigured Code and verify Compliance changes 

1.  Create a pull request 
1.  Merge repository
1.  Validate compliance changes

## END OF LABS

[Return to README](https://github.com/rickdevera/tenable_immersion_day/blob/main/README.md)