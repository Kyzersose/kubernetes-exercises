# Build a k8's cluster

- I'm building one locally via minikube

    # inputs:
    - minikube start
    1. Add the bitnami helm chart repo
    - helm repo add bitnami https://charts.bitnami.com/bitnami
    2. Find the mysql charts
    - helm repo search bitnami/mysql
    3. Look up what's needed to configure mysql: https://artifacthub.io/packages/helm/bitnami/mysql
    4. create a yaml file for mysql configs, mysql-values.yaml
    5. create a secrets file for username/password and add it to gitignore, mysql-secrets.yaml
        - values need to be in base64 ex: "echo -n 'app-user' | base64"
    6. install mysql from bitnami
        - helm install my-release bitnami/mysql -f mysql-values.yaml
    
    