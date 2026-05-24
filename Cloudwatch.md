\- **Monitoring and observability** service used to **collect, monitor, analyze, and visualize logs, metrics, and events** from AWS resources and applications.

\- It helps organizations **monitor infrastructure health, application performance, resource utilization, and automate alerting** and remediation actions.



**# Need :**

In cloud environments, **resources are dynamic**:

\- EC2 instances scale up/down

\- Applications generate logs continuously

\- Failures and performance issues can occur anytime



**# Problem and solution :**

Traditionally, administrators manually:

SSH into servers -> Check CPU/memory -> Read log files -> Monitor applications individually

\- This becomes difficult at scale.



CloudWatch solves this by:

Automatically collecting metrics -> Centralizing logs -> Triggering alerts -> Enabling automated responses



**# CloudWatch collects data from**:

EC2, Lambda, RDS, Load Balancers, Applications, Custom scripts/services



**# It stores:** Metrics, Logs, Events



**# Example :**

\- Suppose an EC2 web server experiences high CPU usage.

CloudWatch monitors CPU continuously

CPU crosses threshold (e.g., 80%)

CloudWatch Alarm triggers

Notification sent via SNS/email

Auto Scaling can launch new EC2 automatically.

