# nodejs-app
Task -Nodejs app 

Create a ci/cd pipeline for a node.js application that: 1.runs test automatically on pull requests 2. Build docker image and deploy it to kubernetes cluster. 3 include notification for deployment success or failure





Why Ci/Cd pipeline fails? Explanation

I deployed kubernetes locally thats why pipeline fails.
Local Kubernetes Access: GitHub Actions cannot access a local Kubernetes cluster directly. 



[If you're running Kubernetes locally, the GitHub Actions runner won't be able to directly access your local cluster unless it's accessible over the internet (e.g., through a public cloud or VPN). Typically, you would need a cloud-based Kubernetes cluster (like Google Kubernetes Engine, Azure Kubernetes Service, etc.) for GitHub Actions to work seamlessly with Kubernetes.]



Configuration for GitHub Secrets
For the pipeline to work correctly, you'll need to configure the following secrets in your GitHub repository:

DOCKER_USERNAME: Your Docker Hub username.
DOCKER_PASSWORD: Your Docker Hub password.
KUBE_CONFIG: Base64-encoded Kubernetes kubeconfig file.
SLACK_WEBHOOK_URL: Slack Incoming Webhook URL for deployment notifications.

Explaining My Approach [Everything Done on Windows]

1.Created  A Simple Node.js Application
2.Created a DockerFile Builded and Ran, Pushed to Docker Hub   [Used Docker Desktop]
3. Created A deployment.yaml to deploy locally in kubernetes cluster [Installed minikube in Windows]
4.Created a Slack App , with incoming webhooks for Notification of Deployment Success or File  [in Chrome]
5.Pushed the code to github
6. Github Actions- setuped a Ci-cd.yml for pipeline and test.yml for Running tests
