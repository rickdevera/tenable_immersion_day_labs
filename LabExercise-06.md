# Lab Exercise 06

## Using Visual Studio Code (VS Code) and Tenable.cs command-Line tools

### Objective:

- I can integrate Tenable.cs with Visual Code Studio
- I can run IaC scans on a local desktop (develop workstation)
- I can run IaC scan across using the CLI

### Prerequisites
- Tenable.io account
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser
- Windows Desktop
- Familiarization of Visual Studio Code
- Completed Labs 1 and 2
____

### Tasks


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

***Note***:  For the most up-to-date steps, follow the steps outlined in the Marketplace page for [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=AccuricsInc.accurics-iac).


1.  *Note:* You will use the project created in Lab 02.  **
.
1.  In the VS Code workspace, select the Tenable.cs extension.
1.  `Click` View > Command Palette.
    - The Command Palette box appears.
1.  `Select` Tenable.cs Mode and then select Integrated.
1.  Access Tenable.cs from https://cloud.tenable.com/.
    - The Tenable.cs Dashboard page appears.
1.  On the Home page, `click` the Projects and Connections tab.
1.  `Click` your project to view its details.
1.  In the upper-right, `click` the Configuration link to download the configuration .zip file and extract it to a local folder.
1.  In the VS Code workspace, `click` View > Command Palette.
1.  From the Command Palette box, `choose` Tenable.cs Configuration and select `the` configuration file that you saved in step above (unzipped file).
1.  `Right-click` on **main.tf**, and `select` **Tenable.cs Scan->init**, `press` enter for defaults
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



[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)