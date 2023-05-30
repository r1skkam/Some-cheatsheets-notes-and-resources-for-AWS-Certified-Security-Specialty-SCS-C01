[Centralized Operations Hub – AWS Systems Manager – Amazon Web Services](https://aws.amazon.com/systems-manager/)

**Manage your resources on AWS and in multicloud and hybrid environments**

```
AWS Systems Manager is a secure end-to-end management solution for resources on AWS and in multicloud
and hybrid environments. 
```

![image](https://github.com/r1skkam/Some-cheatsheets-notes-and-resources-for-AWS-Certified-Security-Specialty-SCS-C01/assets/58542375/0eda538f-91a7-4b00-8acc-34e835dc47fd)

**Session Manager**
```
AWS Systems Manager provides a browser-based interactive shell, CLI and browser based remote desktop access
for managing instances on your cloud, or on-premises and edge devices, without the need to open inbound ports,
manage Secure Shell (SSH) keys, or use bastion hosts. Administrators can grant and revoke access to instances
through a central location by using AWS Identity and Access Management (IAM) policies. This allows you to control
which users can access each instance, including the option to provide non-root access to specified users.
Once access is provided, you can audit which user accessed an instance and log each command to Amazon Simple Storage Service (S3)
or Amazon CloudWatch Logs using AWS CloudTrail.
```

[AWS Systems Manager Documentation](https://docs.aws.amazon.com/systems-manager/index.html)

```
Use AWS Systems Manager to organize, monitor, and automate management tasks on your AWS resources.
```

[ssm &#8212; AWS CLI 1.27.141 Command Reference](https://docs.aws.amazon.com/cli/latest/reference/ssm/index.html)

**Automation**
```
AWS Systems Manager allows you to safely automate common and repetitive IT operations and management tasks.
With Systems Manager Automation, you use predefined playbooks, or you can build, run, and share 
wiki-style automated playbooks to enable AWS resource management across multiple accounts and AWS Regions.
You can run Python or PowerShell scripts as part of a playbook in combination with other automation actions
such as approvals, AWS API calls, or running commands on your EC2 instances. These playbooks can be scheduled
in a maintenance window, triggered based on changes to your resources on AWS and in multicloud and hybrid environments
through Amazon CloudWatch Events, or executed directly through the AWS Management Console, CLIs, and SDKs.
Automation can track the execution of each step in a playbook, require approvals, incrementally roll out changes,
and automatically halt the rollout if errors occur.
```
