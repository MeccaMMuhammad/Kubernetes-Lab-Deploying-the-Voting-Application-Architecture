# Kubernetes-Lab-Deploying-the-Voting-Application-Architecture
This repository contains the YAML configurations used to deploy the Kubernetes-based Voting Application Architecture within the vote namespace.
The lab focused on deploying various services and applications like Redis, Vote, Result, Worker, and Database in Kubernetes clusters, troubleshooting issues, and applying correct solutions to ensure a smooth setup.

Lab Overview

Objective:
Deploy a multi-container application architecture for the "Voting App" on Kubernetes. The architecture consists of several components:

Redis (as a cache service),

Vote (frontend service),

Result (display results service),

Worker (backend worker),

DB (PostgreSQL database).

Each component was deployed as a Kubernetes deployment, and services were configured to expose the deployments.

Challenges Faced:
Service Allocation Issues: Encountered errors like "provided port is already allocated" for NodePort services.

Namespace Misalignment: Initially, the namespace: vote was missing from some YAML files, leading to deployments in the default namespace.

Worker CrashLoopBackOff: The worker container was unable to resolve the database host due to incorrect environment variable configurations, causing it to fail repeatedly.

Cluster Communication Errors: Networking issues due to misconfigured services or incorrect DNS resolutions.

Solution:

Ensured that all resources (deployments, services, etc.) were correctly set under the vote namespace.

Fixed port allocation issues by adjusting the nodePort values.

Debugged worker service and added correct environment variables to resolve host names and ensure communication between services.

