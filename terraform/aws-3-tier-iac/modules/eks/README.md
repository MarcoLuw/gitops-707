# EKS Module
This module deploys an Amazon EKS cluster for running containerized applications using Kubernetes. It includes the necessary resources such as VPC, subnets, security groups, and worker nodes to create a fully functional EKS environment.

## Features
- Creates an Amazon EKS cluster with specified configurations.
- Sets up worker nodes with auto-scaling capabilities.
- Configures networking components including VPC, subnets, and security groups.
- Integrates with IAM for secure access and permissions
- Supports Kubernetes add-ons and monitoring tools.

## Components
- main.tf: Core cluster definition (aws_eks_cluster, logging, encryption)
- variables.tf: Input variables for customization
- outputs.tf: Outputs for cluster information
- versions.tf: Provider and module version constraints
- iam.tf: Cluster + node IAM roles, OIDC provider, IRSA
- node_groups.tf: Managed node groups, launch templates
- addons.tf: EKS add-ons (VPC CNI, CoreDNS, KubeProxy)
- security.tf: SGs, endpoint access, optional KMS key refs
- locals.tf: Naming, tagging, computed variables
- (Options) fargate.tf: Fargate profiles for serverless compute
- (Options) karpenter.tf: Karpenter setup for dynamic node provisioning
- (Options) data.tf: Data sources for existing resources