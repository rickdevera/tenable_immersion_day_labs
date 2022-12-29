On Tenable.cs, follow the link below to setup auto remediation

**Reference**  https://docs.tenable.com/tenablecs/Content/Analysis/Issues/Remediation/Auto-Remediation.htm?Highlight=pull%20requests   

1. Navigate to the Connect to repository page and select the version control workflow.
2. On the Choose onboarding repositories section, select the repository and click the gear icon.
3. In the Advanced settings window, perform the following:
	1. In the IaC Engine Type box, select Terraform or Terragrunt.
	2. (Optional) Click the Enable Webhook toggle to allow Tenable.cs to continuously monitor your repository for any changes.
		- If this option is enabled, Tenable.cs continuously monitors the repositories and triggers an automatic IaC scan for any code change in the monitored branch of the repository.
	3. From the Remediation type drop-down list, select the Auto-remediate option.
		***The behavior of the Auto-Remediate setting depends on the webhook setting in the previous step.***
		- Webhook Enabled — If webhook is enabled, Tenable.cs continuously monitors the repositories in the project. Whenever there is a code change in the monitored branch (through a pull request, merge, or commit), Tenable.cs triggers an automatic IaC scan. If any violations are detected in the IaC scan, Tenable.cs automatically creates a pull request with fixes in that repository.
		- Webhook Disabled — If webhook is disabled, you must manually run an IaC scan. If any violations are detected in the IaC scan, Tenable.cs automatically creates a pull request with fixes in that repository.
	4. Click Save to save the changes.

Tenable.cs scans the IaC code in the specified repository and then automatically adds the remediation code and creates a pull request to merge the changes to the branch, if any violations are found.