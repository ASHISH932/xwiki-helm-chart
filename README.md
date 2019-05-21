# Xwiki-helm-chart

This is a helm chart for deployment of xwiki on Kubernetes

## Installation on Minikube

* First, enable ingress

```bash
minikube addons enable ingress
```
* Setup Mysql

```bash
helm install --name mysql-xwiki --set mysqlRootPassword=xwiki,mysqlUser=xwiki,mysqlPassword=xwiki,mysqlDatabase=xwiki,imageTag=5.7 stable/mysql
```

* Install chart

```bash
git clone https://github.com/ASHISH932/xwiki-helm-chart.git
cd xwiki-helm-chart
helm --debug upgrade -i --force xwiki -f ./xwiki/values.yaml --set image.tag=123 ./xwiki
```

## Usage

Get ip address of minikube 

```bash
ip=$(minikube ip)
curl $ip/xwiki
```
