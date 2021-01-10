HOW TO DEPLOY MYSQL IMAGE and LINK IT TO OTHER APPLICATION
--------------------------------------------------------
REF: https://linoxide.com/containers/deploy-mysql-on-kubernetes/


1. create passcode base 64

echo -n 'Java2020' | base64
SmF2YTIwMjA=

2. Create a mysql-secret.yaml







//Refrence - https://www.middlewareinventory.com/blog/deploy-docker-image-to-kubernetes/#:~:text=%20Steps%20to%20Deploy%20Docker%20Image%20to%20Kubernetes.,the%20container%20from%20image.%20Start%20the...%20More%20

Step1:
----------
a. create the mysql pod creation file" create-mysql-pod1.yml"(attached here) under kubernetis console .
b. in the kubernetis console enter the command shown below.
   >kubectl create -f create-mysql-pod1.yml
   
