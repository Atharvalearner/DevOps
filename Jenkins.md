Jenkins is an open-source automation server used to implement Continuous Integration and Continuous Delivery. It automates software development tasks such as building, testing, and deploying applications. Jenkins follows a Controller-Agent architecture. The Controller acts as the central management server that receives build requests, manages pipelines, stores configuration, schedules jobs, and assigns work to Agents. Agents are machines or containers that execute the actual build, test, and deployment tasks. Jenkins Pipelines, defined in a Jenkinsfile, describe the complete CI/CD workflow as code, including stages such as source code checkout, build, testing, packaging, and deployment. Jenkins plugins extend its functionality by integrating with tools such as GitHub, Docker, Kubernetes, Maven, SonarQube, and cloud platforms. In a typical workflow, a developer pushes code to GitHub, a webhook triggers Jenkins, the Controller assigns the job to an appropriate Agent, the Agent checks out the code, builds and tests the application, creates the deployment artifact, deploys it to the target environment, and finally sends build notifications



\- This setup ensures efficient resource utilization and parallel execution.

\- **Supports multiple programming languages** and tech stacks, including Java, Python, JavaScript, and more.



**# Architecture :**

***1. Master/Controller Server:***

* Central Brain: Acts as the management hub for the entire Jenkins environment.
* The Jenkins Controller is the central management server. It receives build requests, schedules jobs, loads plugins, manages pipelines, stores configuration, and assigns build tasks to appropriate agents.
* It continuously monitors code repositories like GitHub or GitLab for changes and triggers builds when new code is committed.
* Responsibilities: Receives build triggers, Manages pipelines, Stores configurations, Assigns jobs, Monitors agents, Maintains build history



***2. Slave/Agent node:***

* A machine or container that executes the actual tasks (build, test, etc.) assigned by the controller.
* A Jenkins Agent is a machine or container that performs the actual build, test, or deployment tasks assigned by the Controller. Using multiple agents enables parallel execution and supports different operating systems or environments.
* Each agent can have labels describing its capabilities, like "linux," "docker," or "high-memory," helping Jenkins choose the right agent for each job.



***3. Jenkins Job:***

Unit of Work: A single automated task, It is an automated task such as compiling source code, running unit tests, executing scripts, or deploying an application. Jobs can be configured as Freestyle projects or as Pipelines.



***4. Jenkins Plugins:***

Integrate Jenkins with external tools and services such as GitHub, Docker, Kubernetes, Maven, SonarQube, Slack, AWS, and many others, allowing Jenkins to support a wide range of DevOps workflows.



***5. Jenkins Pipeline:***

Defines the complete CI/CD workflow as code using a Jenkinsfile. It automates stages such as source code checkout, build, testing, packaging, and deployment.

