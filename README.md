# micro-integrator-demo-project

Use following command to build your micro-integrator docker image which contains your composite integration application. Note that `1301` below donates your image version.

```docker  build -t wso2/micro-integrator-demo:1301 .```

Update the k8s deployment with the new image;

```sed -i.bak 's#wso2/micro-integrator-demo:latest#wso2/micro-integrator-demo:1301#' k8s-deployment.yaml```

Redeploy the deployment to the k8s cluster;

```kubectl --namespace=wso2 apply -f k8s-deployment.yaml```
