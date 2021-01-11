HOW TO DEPLOY MYSQL IMAGE and LINK IT TO OTHER APPLICATION
--------------------------------------------------------
REF: https://linoxide.com/containers/deploy-mysql-on-kubernetes/


1. create passcode base 64

echo -n 'Java2020' | base64
SmF2YTIwMjA=

2. Create a mysql-secret.yaml

3. Apply the manifest:

$ kubectl create -f mysql-secret.yaml


4. Verify secrets
   kubectl get secrets
   
5. Create the mysql-pod.yaml file to deploy MySQL pod on Kubernetes cluster:

6.Apply the manifest file:

$ kubectl create -f mysql-pod.yaml

7. Verify that the pod is running:

$ kubectl get pod

8. connect to the mysql bash

  kubectl exec k8s-mysql -it -- bash

9. test mysql password on the mysql bash as 

   echo $MYSQL_ROOT_PASSWORD
   
 10. log into mysql 
 
    mysql --user=root --password=$MYSQL_ROOT_PASSWORD

11. create database test;
    use test;
CREATE TABLE `user` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `firstName` VARCHAR(45) NOT NULL,
  `lastName` VARCHAR(45) NULL,
  `age` INT NULL,
  `salary` BIGINT NULL,
  `username` VARCHAR(45) NULL,
  `password` VARCHAR(255) NULL,
  PRIMARY KEY (`id`));
INSERT INTO  user(firstName, lastName , age , salary , username,password )  values("Rama", "Taraka" ,  25 ,  10000 ,  "ramar" ,  "1234");
exit;

12.  create mysql_service.yaml service file to expose mysql_pod to other pods .

13. Apply the manifest to create the service:

$ kubectl create -f mysql-service.yaml

14. verfy the services running

   >kubectl get service
   
15. we need to get the IP Address of mysql pod "k8s-mysql" using below command

$ kubectl get pod k8s-mysql -o template --template={{.status.podIP}}


//Refrence - https://www.middlewareinventory.com/blog/deploy-docker-image-to-kubernetes/#:~:text=%20Steps%20to%20Deploy%20Docker%20Image%20to%20Kubernetes.,the%20container%20from%20image.%20Start%20the...%20More%20

Step1:
----------
a. create the mysql pod creation file" create-mysql-pod1.yml"(attached here) under kubernetis console .
b. in the kubernetis console enter the command shown below.
   >kubectl create -f create-mysql-pod1.yml
   
