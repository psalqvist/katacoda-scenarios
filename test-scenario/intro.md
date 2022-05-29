# Kubernetes beginner tutorial

## Description

Containerized software has seen a big rise in popularity in rescent time. The benefits of using containers has led a number of companies and organizations to move from a monolitic to a microservice architecture. This naturally creates a need for software that enable teams to orchestrate and manage the infrastructure associated with this containerized architecture. Enter Kubernetes.

This is how the service is described at the Kubernetes website:

"Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications."

By letting your containerized Docker applications live in Kubernetes clusters, automatic scaling can be achieved dependent on the current CPU usage.

In this tutorial, you will containerize a simple NodeJS API using Docker, deploy it to Kubernetes using minikube, and expose your endpoints to the external world with a load balancer.

## Learning Objective

- Create a simple NodeJS and express driven API
- Create a Dockerfile
- Build image and push it to Docker Hub
- Create Kubernetes deployment file
- Create a load balancer
- Deploy API to Kubernetes
- Test access to API using curl