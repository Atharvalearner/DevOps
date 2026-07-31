Nagios is an open-source IT infrastructure monitoring tool used to continuously monitor servers, network devices, applications, databases, services, and system resources. It detects failures, monitors performance, and sends alerts whenever a problem occurs, helping administrators maintain high availability and quickly resolve issues.



It continuously checks the health of systems and immediately notifies administrators if something goes wrong.



***# Components***

**1. Nagios Server:**

Think of it as the brain.

Responsibilities: Executes monitoring checks, Collects monitoring results, Displays dashboard, Generates reports, Sends alerts



**2. Host:**

A Host is any device Nagios monitors.

Examples: Linux Server, Windows Server, Router, Switch, Printer, PCs, etc



**3. Service:**

A Service is something running on a Host.

Example: Linux Server Host machine running Services: SSH, Apache, MySQL, CPU, Memory, Disk Nagios checks each service individually.



**4. Nagios plugins:**

Nagios itself doesn't know how to check everything. Instead, it uses plugins.

Small executable programs / functions that perform specific monitoring checks and return a status code to Nagios.

Examples: check\_http, check\_ping, check\_disk, check\_load, check\_cpu, check\_mysql



**5. Agents:**

For Linux: NRPE (Nagios Remote Plugin Executor)

For Windows: NSClient++

These agents allow the Nagios server to execute monitoring checks on remote machines.





***# Example:***

Suppose Apache crashes.

*Customer*

*↓*

*Website Not Opening*

*↓*

*Nagios*

*↓*

*check\_http*

*↓*

*Apache Down*

*↓*

*Critical Alert*

*↓*

*Email Sent*

*↓*

*Administrator Restarts Apache*

