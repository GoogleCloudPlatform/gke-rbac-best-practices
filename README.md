# Sample yaml files for access control in GKE.

This repository contains yaml files that can be used to implement access control in GKE. 2 Roles are defined, the first one is for the CICD pipeline and is intended to be granted to GCP services such as Cloud Build. Therefore, we specify the GPC service account in the role binding. If you want to implement the CICD pipeline by  Jenkins or other services as Pods, please specify the Kubernetes service account. This role is created from "editor" of the cluster role. The other is the role for the security auditor. This is created based on the "view" of the cluster role, and the permissions of view roles and role bindings are added. 

## How to use these sample yaml files

1. Clone it from GitHub.
1. Change a derectory which is craeted.
1. Modify the parts enclosed in <> to suit your environment in RoleBinding files.
1. Apply your yaml files to your gke cluster.

``` shell
git clone https://github.com/GoogleCloudPlatform/gke-rbac-best-practices
cd gke-rbac-best-practices
vi cicd-rolebinding.yaml or security-auditor-rolebinding.yaml
kubectl apply -f your yaml file
```
