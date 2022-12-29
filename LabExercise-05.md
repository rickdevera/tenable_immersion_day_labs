# Lab Exercise 05

## Custom Policy Scanning

### Objective:

- I can View/Export compliance reports
- I can Create a Custom Policy Group
- I can Add Custom Policy Group to Project
- I can Scan custom policy  

### Prerequisites
- Tenable.io account
- Prior knowledge of GitHub - https://docs.github.com/en/get-started/quickstart/hello-world
- Understand use cases of Infrastructure as Code (IaC)
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser

### Tasks

  ____

#### Export Compliance Report  


  1.  On Tenable.cs Dashboard left menu, hover over the Report icons in the left menu and click the icon for Reports 
    -  **Compliance Report** dashboard should be displayed
**Note: you can filter by, cloud provider, benchmarks, projects, cloud accounts and repository
  to produce specific reports.* 
  
#### Filter Benchmarks  
  
  2.  Select *NIST 800-53*  
  3.  Notice the Changes when compliance benchmark  is selected  
  4.  Generate or export a Compliance Report   
  -  Click on **Export->CSV** 
  5.  Select **Detail Report**  

#### Create a Custom Policy Group 
1.  Create custom policy group
  a.  Policy Name:  **awsjam_custom_policy_group**
2.  Search for **Security Groups** and *Enable* the following <u>rules:</u>  
  a.  **Ensure Security Groups do not have unrestricted specific ports open - (SSH,22)**  
  b.  **Ensure no security groups allow ingress from 0.0.0.0/0 to ALL ports and protocols**  
  c.  **Ensure Security Groups do not have unrestricted specific ports open - (HTTP,8080)**  
3.  Save/Create Policy Group

#### Modify Project

1.  Setup the project, **tenable_awsjam_cft_demo** so **awsjam_custom_policy_group** is the **ONLY** <u>Active policy group*</u> defined.
2.  Note the current value of **Failing policies** for **tenable_awsjam_cft_demo**.
3.  Re-run the IaC scan
3.  Note the new value only shows **Security Groups** defined for the policy group - **awsjam_custom_policy_group**.
_____
</p>