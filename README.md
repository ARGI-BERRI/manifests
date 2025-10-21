# manifests

## Initialization

1. Deploy ArgoCD to Kubernetes cluster:

    ```bash
    # Create a namespace for ArgoCD
    kubectl create namespace argocd

    # Install ArgoCD via Helm
    helm repo add argo https://argoproj.github.io/argo-helm
    helm install -n argocd argocd argo/argo-cd
    ```

2. Initialize ArgoCD with `argocd/argocd.yaml`

## Sealed-Secrets

```bash
# Generate a secret key
mise task run kubeseal-secret > kubeseal.pem

# Generate a encrypted secret file
mise task run kubeseal-generate secret.yaml
```
