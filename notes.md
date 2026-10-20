# Build a k8's cluster

- I'm building one locally via minikube

    # inputs:
    - minikube start
    Add the bitnami helm chart repo
    - helm repo add bitnami https://charts.bitnami.com/bitnami
    Find the mysql charts
    - helm repo search bitnami/mysql
    Look up what's needed to configure mysql: https://artifacthub.io/packages/helm/bitnami/mysql
    - create a yaml file for mysql configs, mysql-values.yaml
    - create a secrets file for username/password and add it to gitignore, mysql-secrets.yaml
        - values need to be in base64 ex: "echo -n 'app-user' | base64"