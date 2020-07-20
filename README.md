# detectify-challenge
Repository for Detectify challenge. As a part of the challenge, a simple website was created on kubernetes to display the two separate "strings" on the call of the two separate links
To cater the challenge requirement, I have followed the below steps

1. Created the AWS EKS Cluster through terraform scripts.

2. AWS EKS cluster and worker node was created in the us-east-1 (US East (N. Virginia)) region.

3. A dockerfile was created with Busybox docker image.

4. First index.html file was created with the " Hello World"

5. Build and publish a simple http service which say “Hello world”

6. Build and publish include docker build, tag and push the file to docker hub.

7. Deployed in AWS EKS Kubernetes cluster using a helm chart. 

8. Helm is used as the package manager for Kubernetes and to deploy the above deployment using a single “helm install” command.

9. For the second string display " Hello World, again" , updated in the index.html file.

10. Build the docker file, tag it with the new version "2.0" ans push it to the docker hub.

11. Docker hub was having two tags in the repository rimpaljohal/hello-world. These tags in the repository named as "latest" and "2.0".

12. Helm helloworld-chart files "values.yaml" and "deployment.yaml" was updated for the first deployment in the pod.

13. Helm helloworld-chart files "values.yaml", deployment.yaml" and "chart.yaml" was updated for the second deployment in the pod.

14. Two app deployment was done in two separate pods

  Rimpals-MBP:etc rimpaljohal$ kubectl get svc
NAME                           TYPE           CLUSTER-IP       EXTERNAL-IP                                                               PORT(S)        AGE
helloworld-helloworld-chart    LoadBalancer   10.100.15.80     a283915e7f5394a96a500f30aa10244f-1437370688.us-east-1.elb.amazonaws.com   80:32445/TCP   5h6m
helloworld2-helloworld-chart   LoadBalancer   10.100.132.174   a58f77a4ebab14b57a131f2b58a9f4e7-2025572287.us-east-1.elb.amazonaws.com   80:30284/TCP   42m
kubernetes                     ClusterIP      10.100.0.1       <none>                                                                    443/TCP        5h35m

15. Hosts file in the local machine was mapped with IP address of two ELBs with "challenge.local" and "detectify.challenge.local" to display the two strings in the local PC with the hit of the URLs
  52.55.46.152    detectify.challenge.local
  52.45.58.117    challenge.local
