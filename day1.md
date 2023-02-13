## 1) Add bitnami helm chart repository in the controlplane node. 



```bash 
helm repo add my-repo https://charts.bitnami.com/bitnami
```

## 2) Deploy the Apache application on the cluster using the apache from the bitnami repository ,Set the release Name to: amaze-surf

```bash
helm install amaze-surf my-repo/apache
```

## 3) Uninstall the apache chart release from the cluster.

```bash
helm delete amaze-surf
```

## 4) install specfic version of nginx 1.22.0, then update it to specfic 1.23.1, then rollback.


1) List charts version for nginx
    ```bash
    helm search repo nginx -l | grep 1.22.0 
    ``` 
2) Install version 1.22.0
    ```bash
    helm install nginx-relase my-repo/nginx --version 12.0.6  
    ```
    
3) Upgrade chart version 

```bash 
helm upgrade nginx-relase my-repo/nginx --version=13.2.10 
```
4) Rollback the chart 

```bash
helm rollback nginx-relase 1
```

 
