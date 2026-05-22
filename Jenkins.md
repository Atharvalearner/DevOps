\- **Master-slave** architecture

\- **Automation**: Automates repetitive tasks such as builds, tests, and deployments.

\- Jenkins server (master) manages build jobs and delegates their execution to agent nodes (slaves). 

\- This setup ensures efficient resource utilization and parallel execution.

\- **Supports multiple programming languages** and tech stacks, including Java, Python, JavaScript, and more.

\- Ease of Setup: Provides a user-friendly web-based GUI for configuration.



**Architecture :**

***1. Master/Controller Server:***

\- Central Brain: Acts as the management hub for the entire Jenkins environment.

\- Schedules build jobs and assigns tasks to agents.

\- Handles plugin loading, configuration, and monitoring the health of the system.

\- It stores all the configuration data, including information tasks to run, when to run them, and where to run them.

\- It continuously monitors code repositories like GitHub or GitLab for changes and triggers builds when new code is 

committed.



***2. Slave/Agent node:***

\- A machine or container that executes the actual tasks (build, test, etc.) assigned by the controller.

\- When the master decides a build needs to run, it sends instructions to an available agent, which then executes those instructions.

\- Agents can run on different operating systems (Windows, Linux, etc) allowing you to test application on multiple platforms.

\- Each agent can have labels describing its capabilities, like "linux," "docker," or "high-memory," helping Jenkins choose the right agent for each job.



***3. Jenkins Job:***

Unit of Work: A single automated task, such as a script execution or a project build.

Efficiency: Automates repetitive manual steps to reduce human error and speed up the development cycle.



***4. Jenkins Plugins:***

\- Expand Jenkins' core functionality.

Integration: Connects Jenkins to external tools like GitHub, Slack, Docker, and various cloud providers.



***5. Jenkins Pipeline:***

Workflow as Code: A suite of plugins that lets you define the entire CI/CD process via a script (Jenkinsfile).

End-to-End Automation: Automatically chains together the building, testing, and delivery phases into one continuous flow.

