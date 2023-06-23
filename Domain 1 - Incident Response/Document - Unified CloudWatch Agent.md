# Document - Unified CloudWatch Agent

## Pre-Requisites:

EC2 instance with Appropriate IAM Role (CloudWatchAgentServer Policy)

**Step 1: Install Unified CloudWatch Agent**

```
yum install amazon-cloudwatch-agent
```

**Step 2: Run the Agent Configuration Wizard:**

```
/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard
```

**Step 3: Start CloudWatch Agent**

```
/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s
```

### Documentation Referred:

https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-commandline-fleet.html

https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create-cloudwatch-agent-configuration-file-wizard.html
