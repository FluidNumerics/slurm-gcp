# Overview

This example deploys a [fluid-slurm-gcp](https://console.cloud.google.com/marketplace/product/fluid-cluster-ops/fluid-slurm-gcp) cluster using [Terraform](https://terraform.io).

The fluid-slurm-gcp cluster comes with a suite of compilers and an associated build of OpenMPI 4.0.5
* GCC 7.2.0, 8.4.0, 9.2.0, 10.2.0
* Intel OneAPI Compilers (2021.2.0)

This deployment uses VM images that are licensed to you under the [Fluid-Slurm-GCP EULA](https://help.fluidnumerics.com/slurm-gcp/eula), which entitles you to basic support from Fluid Numerics LLC. You can reach out to support@fluidnumerics.com to obtain support in using this deployment. 

Use of the VM images with this deployment applies a licensing fee that is based on your usage on Google Cloud :
* $0.006638 USD/vCPU/hour
* $0.0945 USD/GPU/hour

This fee enables Fluid Numerics to provide you support.

# Configuration

## tf/examples/singularity/basic.tfvars

Supply values for
- cluster_name: the name of cluster you will deploy to GCP
- project: the GCP project that will host your cluster resources
- zone: the GCP zone where your cluster resources will be deployed
- partitions: information about the Slurm partitions your cluster makes available to cluster users

## tf/examples/singularity/custom-controller-install

Supply values for
- `PROJECT_ID` : The GCP project ID where you are deploying the cluster. This is needed to pull input deck data from a publicly available GCE bucket. 

# Deployment

```terraform init```  
```make apply```

# Teardown

```make destroy```
