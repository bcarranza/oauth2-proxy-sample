# OAuth2 Proxy Sample

This project demonstrates how to set up OAuth2 Proxy with Minikube, Kustomize, and Auth0.

## Prerequisites

- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Kustomize](https://kustomize.io/)
- [OAuth2 Proxy](https://oauth2-proxy.github.io/oauth2-proxy/)
- [Auth0 Account](https://auth0.com/)

## Setup Instructions

### 1. Start Minikube

Start Minikube with the following command:

```sh
minikube start
```

### 2. Create Namespace

Apply the namespace configuration:

```sh
kubectl apply -f namespace.yaml
```

### 3. Create Secrets

Replace the placeholders in `secrets.yaml` with your base64-encoded secrets and apply the configuration:

```sh
kubectl apply -f secrets.yaml
```

### 4. Configure OAuth2 Proxy

Update the OAuth2 Proxy configuration with your Auth0 credentials.

### 5. Deploy with Kustomize

Use Kustomize to deploy the application:

```sh
kustomize build . | kubectl apply -f -
```

### 6. Access the Application

Get the Minikube IP and access the application:

```sh
minikube ip
```

Open your browser and navigate to the Minikube IP.

## Cleanup

To delete the Minikube cluster, run:

```sh
minikube delete
```

## Additional Resources

- [OAuth2 Proxy Documentation](https://oauth2-proxy.github.io/oauth2-proxy/)
- [Auth0 Documentation](https://auth0.com/docs/)
