## Creating Helm chart for the application (Postgres & nestjs)

#### This project has been tested on AWS EKS cluster and it works correctly without any issue

### Before you start deploying this application on the AWS EKS cluster you have to setup the following
### Install Nginx controller
```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx                        
helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx \
  --create-namespace \
  --set controller.service.type=LoadBalancer \
  --set controller.service.annotations."service\.beta\.kubernetes\.io/aws-load-balancer-type"="nlb"
```
### Install and configure AWS EBS Driver
```bash
You can go to the project that teach you how to install it..
```
### Clone git repository that contain our application helm chart project then install it
```bash
git clone https://github.com/oussamabalbal1/project-p3
cd project-p3
helm install app app
```