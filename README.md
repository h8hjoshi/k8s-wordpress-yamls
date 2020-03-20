### Deployment Journal

The repository conatins YAML files to deploy a Wordpress application in a Kubernetes cluster.

1. Create the Secret and ConfigMap
    ```
    kubectl apply -f 00-secret-mysql.yml
    kubectl apply -f 01-configmap-mysql.yml
    ```

2. Create deployments for MySQL and Wordpress
    ```
    kubectl apply -f 02-deployment-mysql.yml
    kubectl apply -f 03-deployment-wordpress.yml
    ```

3. Expose the MySQL pod(s) as a ClusterIP MySQL on port 3306
    ```
    kubectl apply -f 04-service-mysql.yml
    ```

4. Expose the Wordpress pod(s) as a NodePort service
    ```
    kubectl apply -f 05-service-wordpress.yml
    ```
