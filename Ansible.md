Ansible is an **agentless, open-source automation tool** that uses **YAML playbooks** to define and **enforce the desired state** of infrastructure and applications.



It's an **open-source** IT automation tool used for:

&#x09;- **Provisioning** infrastructure

&#x09;- Configuration management

&#x09;- Application deployment

&#x09;- Orchestration of workflows

It is **agentless**, meaning:

&#x09;- **No software required on target nodes**

&#x09;- Uses SSH (Linux) / WinRM (Windows)

**Ansible ensures: System reaches desired state And remains consistent**



Key Features :

1. Open-source \& free

2\. Agentless architecture

3\. **Idempotency**

4\. Cross-Platform : supports Linux, Windows, macOS, Switches, routers, etc

5\. Reduces setup complexity

6\. Simple \& human-readable

7\. Uses **YAML-based playbooks**

8\. Inventory Management : Inventory files (Stores IP Mappings of target / client machines) used to define groups of hosts and their associated variables.





Architecture Components :

1. **Modules** : Units of work that Ansible executes on the managed/client nodes. eg. file ops, pkg installation. Usually written in Python (can be any executable script)
2. **Plugins** : Used to extend Ansible functionality. Types : Action, Connection, Callback, Lookup
3. **Playbooks** : Written in YAML, Define automation workflows, specifying the tasks to execute.
4. **Facts** : System information gathered from managed/client nodes. Collected using the setup module, These facts can be used as variables in playbooks.
5. **Vault** : Used to encrypt sensitive data. Protects: Passwords, API keys. Can be safely used inside: Playbooks, Inventory files.





Workflow : 

1. Prepare Inventory : Define target hosts in inventory file, Grouping them
2. Write Playbooks : YAML used to define desired tasks
3. Execute Playbooks
4. Connect to Managed/client nodes : use SSH or WinRM
5. Task Execute on Managed/client nodes, tasks are idempotent
6. Report Results : Output sent back to control node. Shows: Success / Failure, Changes made

