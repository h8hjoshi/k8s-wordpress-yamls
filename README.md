### Deployment Journal

The repository conatins YAML files to deploy a Wordpress application in a Kubernetes cluster.

1. Create the Secret and ConfigMap
    ```
    kubectl apply -f 00-secret-mysql.yml
    kubectl apply -f 10-configmap-mysql.yml
    ```

2. Create a persistent volume (local file system)
    ```
    kubectl apply -f 05-persistent-volume.yml
    ```

3. Create a persistent volume claim for the PV
    ```
    kubectl apply -f 06-persistent-volume-claim.yml
    ```

4. Create deployments for MySQL and Wordpress
    ```
    kubectl apply -f 20-deployment-mysql.yml
    kubectl apply -f 30-deployment-wordpress.yml
    ```

5. Expose the MySQL pod(s) as a ClusterIP MySQL on port 3306
    ```
    kubectl apply -f 40-service-mysql.yml
    ```

6. Expose the Wordpress pod(s) as a NodePort service
    ```
    kubectl apply -f 50-service-wordpress.yml
    ```