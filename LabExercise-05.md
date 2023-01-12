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

[Return to Wiki Home Page](https://github.com/rickdevera/tenable_immersion_day_labs/wiki)