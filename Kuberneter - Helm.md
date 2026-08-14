Helm is a package manager for Kubernetes. It uses packages called Helm Charts to define, configure, and deploy Kubernetes applications. A chart contains Kubernetes resource templates and configurable values in files such as values.yaml. Helm helps automate application installation, upgrades, versioning, and rollbacks, and it is commonly integrated with CI/CD pipelines for Kubernetes deployments. Helm 3 communicates directly with the Kubernetes API and does not require Tiller.





**# Why do we use Helm?**

We use Helm to simplify and standardize Kubernetes application deployment. Instead of manually managing multiple YAML files, we package them into a reusable chart, parameterize environment-specific values, and use Helm to install, upgrade, and rollback the application.



**# Real-world example**

Suppose your vulnerability project has:

Frontend, Backend, Elasticsearch, Kibana



You could create:

vulnerability-platform/

│

├── Chart.yaml

├── values.yaml

│

└── templates/

&#x20;   ├── frontend-deployment.yaml

&#x20;   ├── frontend-service.yaml

&#x20;   ├── backend-deployment.yaml

&#x20;   ├── backend-service.yaml

&#x20;   ├── elasticsearch.yaml

&#x20;   └── ingress.yaml



Then deploy everything using:

helm install vulnerability-platform ./vulnerability-platform



For another environment:

helm install vulnerability-platform-test ./vulnerability-platform -f values-test.yaml



And production:

helm upgrade --install vulnerability-platform-prod ./vulnerability-platform -f values-prod.yaml



So one reusable chart can manage multiple environments.





| Kubernetes                              | Helm                                         |

| --------------------------------------- | -------------------------------------------- |

| Container orchestration platform        | Kubernetes package manager                   |

| Manages containers/workloads            | Packages and manages Kubernetes applications |

| Uses YAML manifests                     | Uses templated YAML/Charts                   |

| Provides Deployment, Service, Pod, etc. | Simplifies management of those resources     |

| Can work without Helm                   | Helm depends on Kubernetes for deployment    |



**# Think of it as:**

Kubernetes = Platform that runs the application

Helm = Tool that packages and manages the application on Kubernetes

