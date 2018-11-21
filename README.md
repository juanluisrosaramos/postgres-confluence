# Deploying in Kubernetes a Confluence with Postgres instance

Following this tutorial at https://cloud.google.com/kubernetes-engine/docs/tutorials/persistent-disk/

Create the cluster gcloud container clusters create conflue-mysql --num-nodes=3

Create persistent volumes for permanent storage. Edit the yaml files for changing storage space
kubectl apply -f postgres-volumeclaim.yaml
kubectl apply -f confluence-volumeclaim.yaml


Charge the GKE cluster with configuration with $gcloud container clusters get-credentials name-cluster

Set secret variables with:
kubectl create secret generic postgres --from-literal=dbname=YOUR_DB_NAME --from-literal=username=YOUR_USERNAME --from-literal=password=YOUR_PASS




