# EKS

Implementation of EKS setup using `Terraform`.

Templates support deployment to different AWS partitions. I have tested it with `public` and `china` partitions. I am actively using this configuration to run EKS setup in Ireland(eu-west-1), North Virginia(us-east-1) and Beijing(cn-north-1).

### Terraform



## Kubernetes addons and operators

I am utilising Flux2 to deploy all additional configurations. You can find them at https://github.com/marcincuber/kubernetes-fluxv2
I have built this as a separate repository to show how to develop a successful configuration for your cluster using GitOps FluxV2 and Helm.

You will find configurations for:

* ALB ingress controller
* AWS Load Balancer controller
* AWS node termination handler
* Calico
* Cert Manager
* Cluster Autoscaler
* Dashboard
* External-DNS
* External Secrets Operator
* Metrics server
* Reloader
* VPC CNI Plugin
* EBS CSI Driver
* and more :)

## Docs and other additional resources

Check out my stories on medium if you interested in finding out more on specific topics.

### Amazon EKS upgrade 1.26 to 1.27

[Amazon EKS upgrade journey from 1.26 to 1.27](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-26-to-1-27-chill-vibes-46f3f979afac)

### Amazon EKS upgrade 1.25 to 1.26

[Amazon EKS upgrade journey from 1.25 to 1.26](https://medium.com/@marcincuber/amazon-eks-upgrade-journey-from-1-25-to-1-26-electrifying-79b287084eef)

### Amazon EKS upgrade 1.24 to 1.25

[Amazon EKS upgrade journey from 1.24 to 1.25](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-24-to-1-25-e1bcccc2f384)

### Amazon EKS upgrade 1.23 to 1.24

[Amazon EKS upgrade journey from 1.23 to 1.24](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-23-to-1-24-b7b0b1afa5b4)

### Amazon EKS upgrade 1.22 to 1.23

[Amazon EKS upgrade journey from 1.22 to 1.23](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-22-to-1-23-3b9eaa8c57de)

### Amazon EKS upgrade 1.21 to 1.22

[Amazon EKS upgrade journey from 1.21 to 1.22](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-21-to-1-22-9546da932af6)

### Amazon EKS upgrade 1.20 to 1.21

[Amazon EKS upgrade journey from 1.20 to 1.21](https://marcincuber.medium.com/amazon-eks-upgrade-journey-from-1-20-to-1-21-caf1475deaa4)

### Amazon EKS Addons
[Amazon EKS Addons](https://marcincuber.medium.com/amazon-eks-add-ons-implemented-with-terraform-66a49fad4174)

### EKS + Kube-bench

[Kube-bench implementation with EKS](https://itnext.io/aws-eks-and-kube-bench-a7ae840f0f1)

### Amazon EKS design, use of spot instances and cluster scaling

More about my configuration can be found in the blog post I have written recently -> [EKS design](https://medium.com/@marcincuber/amazon-eks-design-use-of-spot-instances-and-cluster-scaling-da7f3a72d061)

### IAM Roles for specific namespaces

[Amazon EKS- RBAC with IAM access](https://medium.com/@marcincuber/amazon-eks-rbac-and-iam-access-f124f1164de7)

### IAM Roles for service accounts using OpenID Connect

[Using OIDC provider to allow service accounts to assume IAM role](https://medium.com/@marcincuber/amazon-eks-with-oidc-provider-iam-roles-for-kubernetes-services-accounts-59015d15cb0c)

### Kube2iam

More about kube2iam configuration can be found in the blog post I have written recently -> [EKS and kube2iam](https://medium.com/@marcincuber/amazon-eks-iam-roles-and-kube2iam-4ae5906318be)

### External DNS

[Amazon EKS, setup external DNS with OIDC provider and kube2iam](https://medium.com/swlh/amazon-eks-setup-external-dns-with-oidc-provider-and-kube2iam-f2487c77b2a1)

### EKS Managed Node Groups

[Amazon EKS + managed node groups](https://itnext.io/amazon-eks-managed-node-groups-87943e3f3360)

Terraform module written by me can be found in -> https://registry.terraform.io/modules/umotif-public/eks-node-group

### Gitlab runners on EKS

[Kubernetes GitLab Runners on Amazon EKS](https://medium.com/@marcincuber/kubernetes-gitlab-runners-on-amazon-eks-5ba7f0bff30e)

### Useful resources

[EKS platforms information](https://docs.aws.amazon.com/eks/latest/userguide/platform-versions.html)
[Worker nodes upgrades](https://docs.aws.amazon.com/eks/latest/userguide/update-stack.html)

## Generate kubeconfig file

On user's machine who has been added to EKS, they can configure .kube/config file using the following command:

```bash
$ aws eks list-clusters
$ aws eks update-kubeconfig --name ${cluster_name}
```

