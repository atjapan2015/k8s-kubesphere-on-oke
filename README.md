# Install KubeSphere on OKE

### Install KubeSphere using kubectl. The following commands are only for the default minimal installation.

```sh
kubectl apply -f https://github.com/kubesphere/ks-installer/releases/download/v3.0.0/kubesphere-installer.yaml

kubectl apply -f https://github.com/kubesphere/ks-installer/releases/download/v3.0.0/cluster-configuration.yaml
```

### Inspect the logs of installation:

```sh
kubectl logs -n kubesphere-system $(kubectl get pod -n kubesphere-system -l app=ks-install -o jsonpath='{.items[0].metadata.name}') -f
```

### When the installation finishes, you can see the following message:

```
#####################################################
###              Welcome to KubeSphere!           ###
#####################################################

Console: http://10.0.10.2:30880
Account: admin
Password: P@88w0rd

NOTES：
  1. After logging into the console, please check the
    monitoring status of service components in
    the "Cluster Management". If any service is not
    ready, please wait patiently until all components 
    are ready.
  2. Please modify the default password after login.

#####################################################
https://kubesphere.io             20xx-xx-xx xx:xx:xx
```



