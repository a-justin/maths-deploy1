# Maths Deploy 1

## Overview
Maths Deploy 1 is best suited for automating the deployment of mathematical or analytics applications using Kubernetes and GitOps principles. It streamlines the local and continuous deployment process, making it ideal for developers or teams seeking a reproducible, easy-to-manage deployment workflow for their containerized applications on Windows via Minikube and Argo CD.

## Features
- Rapid local Kubernetes development setup using Minikube.
- Continuous, declarative deployment via Argo CD.
- Windows-friendly (optimized for Powershell Terminal usage).
- Simple integration with Git-based workflows.
- Easily adaptable for mathematical or analytical workloads.

## Installation
To get started with this project, follow the installation instructions below:

```bash
# Clone the repository
git clone https://github.com/a-justin/maths-deploy1.git

# Navigate to the project directory
cd maths-deploy1

# Install dependencies
npm install
```

## Usage
To run the project locally, use the following command:

```bash
npm start
```

## Deployment
This project was deployed using the following stack:

- **Kubernetes (Minikube)**: Local Kubernetes environment for easy testing
- **Argo CD**: Declarative, GitOps continuous delivery for Kubernetes
- **Powershell Terminal**: Used for running Minikube and Argo CD commands on Windows

### Steps to Deploy with Minikube and Argo CD

1. **Start Minikube:**
    ```powershell
    minikube start
    ```
2. **Enable Ingress (optional):**
    ```powershell
    minikube addons enable ingress
    ```
3. **Install Argo CD:**
    ```powershell
    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
    ```
4. **Expose Argo CD UI:**
    ```powershell
    kubectl port-forward svc/argocd-server -n argocd 8080:443
    ```
5. **Login to Argo CD:**
    Visit http://localhost:8080 and log in (default username: admin, password from `kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d`)
6. **Connect your repository and deploy your app via Argo CD UI or CLI.**

You can refer to Argo CD and Minikube documentation for troubleshooting and advanced scenarios.

## Contributing
We welcome contributions to this project. Please follow the guidelines below:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
Austin
