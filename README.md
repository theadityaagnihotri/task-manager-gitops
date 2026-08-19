# task-manager-gitops

GitOps configuration repository for the Task Manager API.

## Principle

This repository is the **single source of truth** for what should be running
in the Kubernetes cluster. Argo CD continuously watches this repo and
reconciles the live cluster state to match it — no manual `kubectl apply`
or `helm upgrade` is used for deployments.

- **Desired state**: whatever is committed here (`values.yaml`, templates)
- **Actual state**: whatever is currently running in the cluster
- **Reconciliation**: performed automatically by Argo CD

## Structure

- `task-manager/` — Helm chart defining the Deployment, Service, Ingress,
  ConfigMap, and ServiceAccount for the Task Manager API

## Related repository

Application code and CI pipeline: [task-manager-api](https://github.com/theadityaagnihotri/task-manager-api)
