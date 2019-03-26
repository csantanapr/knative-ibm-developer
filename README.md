# Build your first app on Knative Serverless
In this live webcast, you'll learn about Knative, a new open source collaboration from IBM, Google, Pivotal, Red Hat, Cisco, and others. Knative is a Serverless platform that offers a set of reusable components that focuses on solving many mundane but difficult tasks such as orchestrating source-to-container workflows, routing and managing traffic during deployment, auto-scaling your workloads, or binding running services to eventing ecosystems.

Webinar details here: https://developer.ibm.com/events/build-your-first-app-on-knative-serverless-online-3-26-2019/

## Install Knative
Depending which Kubernetes deployment you have follow the instructions here https://www.knative.dev/docs/install/

I recommend using the IKS (IBM Kubernetes Service) Knative Add-on https://www.ibm.com/blogs/bluemix/2019/03/knative-on-ibm-cloud-kubernetes-service-your-first-app-now-even-easier/

## Deploy Go App
Build the container image
```bash
pushd go
docker build . -t {username}/helloworld-go
docker push {username}/helloworld-go
popd
```
Deploy the Knative service, but first edit the docker image location replacing it with your `{username}` from previous step.
```bash
kubectl apply -f service-go.yaml
```
Verify the deployment
```bash
kubectl get ksvc
```
Run the App, first get the URL of the App
```bash
kubectl get routes
```
Open the App in a Browser or use Curl usign URL from previous step

## Deploy Node.js App
Build the container image
```bash
pushd nodejs
docker build . -t {username}/webappnodejs-express-run
docker push {username}/webappnodejs-express-run
popd
```
Deploy the Knative service, but first edit the docker image location replacing it with your `{username}` from previous step.
```bash
kubectl apply -f service-nodejs.yaml
```
Verify the deployment
```bash
kubectl get ksvc
```
Run the App, first get the URL of the App
```bash
kubectl get routes
```
Open the App in a Browser or use `curl` usign URL from previous step

## Deploy Java App
Build the container image
```bash
pushd nodejs
docker build . -t {username}/quarkus
docker push {username}/quarkus
popd
```
Deploy the Knative service, but first edit the docker image location replacing it with your `{username}` from previous step.
```bash
kubectl apply -f service-java.yaml
```
Verify the deployment
```bash
kubectl get ksvc
```
Run the App, first get the URL of the App
```bash
kubectl get routes
```
Open the App in a Browser or use `curl` usign URL from previous step