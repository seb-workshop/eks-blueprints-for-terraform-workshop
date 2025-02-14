---
title: 'Clean up'
weight: 90
---


In this workshop, we created a VPC, then 2 or more clusters. The EKS clusters were created using Terraform, but the Applications were deployed using ArgoCD.

As Terraform does not know what ArgoCD Applications are installed on each EKS cluster, we need to clean thoses applications before destroying the clusters with Terraform.

To ease this, we prepared a `destroy.sh` script, that will clean properly the installed resources in appropriate order.

If you have deployed additional resources, that may have created Wloud resources, you also need to clean them prior to destroy the clusters, otherwise thoses resources may be not cleaned properly.

### Use the cleanup script.

You can just execute the cleanup script. In this script, there can be somme errors, but that is normal and the script will repeat some of the actions until normally cleanup sucess.

```bash
~/environment/wgit/assets/scripts/destroy.sh 
```


::alert[Removing resources in this specific order ensures dependencies are deleted entirely.  VPCs, subnets, and IP addresses attached to ENIs are all deleted last.]{header="Important"}


> Congratulations! You should have removed everything installed by the workshop.