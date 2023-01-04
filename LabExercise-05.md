# Lab Exercise 05

## Custom Policy Scanning

### Objective:

- I can View/Export compliance reports
- I can Create a Custom Policy Group
- I can Add Custom Policy Group to Project
- I can Scan custom policy  

### Prerequisites
- Tenable.io account
- Skills
  - Prior knowledge of networking, and Microsoft Windows and browser
- Completed Labs 1 and 2

### Tasks

  ____

#### Compliance Report Dashboard


  1.  On Tenable.cs Dashboard left menu, `click` the icon for Reports 
  1.  Under *Projects*, `select` the project defined in <u>**Lab 02 (eg.  iac_demo_project)**</u>
  1.  `Select` **Filters**
      1.  `Enable` filter on 
          - Policy Status:  **Non-Compliant**
          - Severity:  **High**
  1.  `Expand` the control *Infrastructure Security*
  1.  `Click` on the *Policy Name* **Ensure Security Groups do not have unrestricted specific ports open - (SSH,22)**
  
  ## VALIDATION QUESTION
  1.  What is the recommended remediation for the violated policy?
  1.  How would you go about remediating the violated policy?  


  ### Create a Custom Policy Group

1.  On the Tenable.cs dashboard, *Create* a new **Custom Policy**
    1.  `Click` on the left menu (+) and select **Custom Policy**
    1.  `Select` **Add Policy Group**
    1.  `


  1.  Under the Benchmark section, `select` the pulldown menu and `search` for **NIST 800-53**

  
#### Filter Benchmarks  
  
  2.  `Select` **NIST 800-53**  
  3.  Notice the Changes when compliance benchmark  is selected  
  4.  Generate or export a Compliance Report   
  -  `Click` on **Export->CSV** 
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