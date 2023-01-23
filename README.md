# This is a deployment of a wordpress instance using helm
- **This documentation walks us through helm</br>**
- **Lets examine the basic command used for this deployment</br>**
- **Ensure you download the chart from artifact hub</br>**
- **Click the link below and follow the corresponding snippet afterwards.**
[helm website for this image](https://artifacthub.io/packages/helm/bitnami/wordpress)
```
  helm repo add my-repo https://charts.bitnami.com/bitnami
  helm install wordpress my-repo/wordpress --values=wordpressvalues.yaml --version 15.2.31
  export NODE_PORT=$(kubectl get --namespace default -o  jsonpath="{.spec.ports[0].nodePort}" svc wordpress)
  export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
  echo "WordPress URL: http://$NODE_IP:$NODE_PORT/
  echo "WordPress Admin URL: http://$NODE_IP:$NODE_PORT/admin"
  curl http://192.168.28.253:31720/admin
  
```
