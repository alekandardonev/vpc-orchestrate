<h1 align=""> EKS Setup Example with Terraform :package: :whale: :rocket:  </h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-v0-blue.svg?cacheSeconds=2592000" />
  <a href="/" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  
  <a href="Terraform Compatibility" target="_blank">
    <img alt="Build" src="https://github.com/msfidelis/eks-terraform-orchestration/workflows/Terraform%200.12.*%20compatibility/badge.svg?branch=master" />
  </a>
  
  <a href="https://twitter.com/fidelissauro" target="_blank">
    <img alt="Twitter: fidelissauro" src="https://img.shields.io/twitter/follow/fidelissauro.svg?style=social" />
  </a>
</p>

> Easy Way to Setup EKS with Ingress Controller like Nginx, Traefik, Envoy e etc


This repo contains methods to deploy this resources on Amazon EKS 

* Custom Ingress Controller behind the ALB 
* Jaeger to improve observability 
* Deployment methods for infraestructure and applications

Enjoy and customize to your use case 


### 🏠 [Homepage](/)

### ✨ [Demo](/)

## Install

```sh
git clone git@github.com:msfidelis/eks-terraform-setup.git
```

## Usage

This repo should be used like template or reference to your project.


### Edit variables.tf

```sh
vim variables.tf
```

### Apply 

```sh
terraform plan
terraform install --auto-approve
```

### Configure credentials to local workstation or bastion host 

```sh
aws eks --region {region} update-kubeconfig --name {cluster name}
aws eks --region us-east-1 update-kubeconfig --name k8s-demo
```

## Deploy applications for this demo 

```sh
cd kubernetes/applications/
kubectl apply -f *
```

## Choose your ingress

### Available flavors 

* Traefik
* NGINX 
* Haproxy
* Gloo 
* Ambassador
* Kong
* Contour

```sh
cd kubernetes/ingress/{your flavor}/
```

### Deploy your ingress controller as Daemonset

```sh
kubectl apply -f ingress.yml
```

### Deploy the ingress rules

```sh
kubectl apply -f rules.yml
```

## Run tests

```sh
terraform validate
```
