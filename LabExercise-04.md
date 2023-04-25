## Scanning for Vulnerabilities

###  Description
Securing cloud resources and cloud runtimes requires a different approach vs. traditional on-premise or less
ephemeral systems. Auto-scaling and automated provisioning means instances come and go and can be
missed by traditional scans. Tenable Cloud Security combines cloud security posture and vulnerability management
into a single solution. Agentless Assessment is a Cloud Vulnerability Management solution designed to
meet the unique challenges posed by cloud-native environments. It uses APIs – not agents – to
automatically detect and analyze newly created instances using a single read-only role to gather and report
on misconfigurations and vulnerabilities. It scans instance snapshots instead of the instances themselves,
so there’s <u>no impact</u> on running systems. Data is securely analyzed in the users’ workspaces, and scan results
are available for teams to review in shared dashboards and reports.

#### Task Summary

- Create EBS snapshots
- Scan Profiles with Tenable Agentless Assessment
- Verify vulnerabilities on EBS Snapshots for EC2 instances
___
**Documentation Notes:**
- Tenable.cs is used interchangeably with Tenable Cloud Security
- Tenable.io is used interchangeably with Tenable Vulnerability Management
_____

### Prerequisites


### Tasks

#### 1.  Create Snapshots
This is a prerequisite before you set up an Agentless Assessment. Create snapshots for EC2 instances that you want to scan.  The Agentless Assessment process requires them to read installed package data. (Not covered in this lab:  You can create snapshots manually, or you can automate the process using <u>AWS Data Lifecycle Manager (DLM).</u> )

1.  On the AWS console
    1.  Go to the **EC2 Dashboard**, validate Instance Name **AA_EC2_Demo**  exists
    1.  Go to **Elastic Block Store->Snapshot**  ,
    1.  `Click` on **Create snapshot**,
    1.  `Click` on the **Instance** radio button,
    1.  `Click` on the ***Instance ID*** dropdown menu,
    1.  `Search` for **AA_EC2_Demo**,  
    1.  Select the Instance ID for **AA_EC2_Demo**, 
    1.  Enter a description:  **Agentless Demo EC2 Snapshot**,
    1.  `Click` on **Create snapshot**,   
    **Note:** This may take a few minutes.  
  g.  `Click` the refresh button and **WAIT** for the <u>Snapshot Status</u> to display status as **Completed**.  


#### Setup a Project and Scan Profile

Scan profiles allow you to group the scan operations of different cloud resources and schedule scans according to your needs. You can create different scan profiles to run scans targeting different resources. For example, you can create a scan profile to run a scan targeting only Vulnerability Scans of EC2 instances.

In this you will enable the **Vulnerability Scan Option**.  When you enable vulnerability scan, Tenable.cs starts scanning EC2 instances for vulnerabilities after the misconfiguration scan completes.

1.  One the Tenable Cloud Security Dashbord:  
  1.  `Create` a project (Lab03-Project),
      1.  Click on the (+) button on the left menu , 
      1.  Enter the project name: **AA_demo** , 
      1.  Select **AWS**,
      1.  Click on **Create**,
1.  `Click` on the project.
1.  `Click` on the *pencil* icon next to **Cloud accounts**,  
1.   `Select` the **Cloud account** that was created in the previous lab.
1.  `Click` the **kebab** button, `Select` **Manage cloud scan profiles**.
1.  `Click` on the **kebab** button, `Select` **Set as default profile**
1.  `Click` on the **kebab** button, `Select` **Duplicate**
1.  `Select` the new profile and **Edit** the profile  
  1.  Change the profile name to **Lab03-profile**, 
  1.  Clear all selection  
    1.  `Click` on **Select all**,  
    2.  `Click` on **Clear all**.  
  1.  `Enable` **Computer->EC2 Instance**,
  1.  Under <u>Step 2</u>, `Slide` the **Enable Vulnerability Scan** button on **ON**.
  1.  **Save** the profile.

#### Scan the Snapshot
1.  `Select` the **kebab** for the project:  
    1.  `Click` on **Run default cloud scan profile**
    **Note**:  This step may take 15-20 minutes.
1.  `Refresh` the main Dashboard screen.

#### View Vulnerabilities

Scanning for known vulnerabilities (CVEs) in workloads, such as operating systems, images, containers, and software based on plugins, is an industry best practice in maintaining the security and integrity of the cloud infrastructure.

Vulnerabilities can be used and exploited by cyber attackers to gain unauthorized access to systems.  It's important to scan on a regular basis and to record and display the risk: Tenable Cloud Security will provide data such as severity level, plug-ins impacted, advisories and the impact, and vulnerability priority ratings (VPR) (to quantify the risk and urgency of a vulnerability.)


1.  `Click` the **Resources** button from the *left menu*,
1.  `Select` filters:
    1.  **Projects->Lab03-Projects**,
    1.  **Cloud accounts->\.
1.  `Click` on the **Resource ID** for **AA_EC2_Demo**,
1.  `Expand` the **Vulnerabilities** heading,
1.  `Click` on the **Severity** button and `Deselect` <u>**ALL**</u> except the **Critical**  severity,
1.  `Click` on the *URL link* for **<u>Ubuntu 12.04 LTS / 14.04 LTS / 14.10 : icu vulnerabilities (USN-2522-1)</u>**.


### VALIDATION QUESTION

1.  By navigating through the details of **<u>Ubuntu 12.04 LTS / 14.04 LTS / 14.10 : icu vulnerabilities (USN-2522-1)</u>**, can you explain why the plugin security issues?

<!--
Plugins contain vulnerability information and scans detect the presence of vulnerabilities -->

## End of Lab 

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)