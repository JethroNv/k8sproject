# Kubernetes-wp-project-On-AWS
This project deploys wordpress using mysql database on AWS using kubernetes.

After creating my ec2 ubuntu instance on AWS with an EBS of 30 Gi,
I ssh into the instance from my local ubuntu using the public IP.

I install docker and k3s on the ec2 ubuntu instance.

I then created and deployed the yaml files in this order:

1. devopsnamespace.yml #the name space yaml file
2. pvc.yml #the persistent volume claim
3. mysql-deployment.yml #the mysql deployment file with its service
4. wordpress-deployment.yml #the wordpress deployment yaml file with its service
All these were deployed in the same namespace (dev) for them to communicate with each other)


use this to switch context to dev namespace
kubectl config set-context --current --namespace=dev

Use kubectl get all
to check that the deployments and services are running as expected.

Then I used the my public IP from my ec2 instance with the nodeport (which in this case is 30080) on a browswer to install and configure my wordpress