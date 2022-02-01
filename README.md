# Forked from steve-caron-dynatrace/dynatrace-k8s from se-bootcamp-2019

## Updates made to this fork
1. Manifests updated in support of Kubernetes version 1.21.x where extensions/v1beta1 API is no longer supported and switched to apps/v1. 1.21.x also requires a spec selector so have added that.

2. Added a standalone IBM ACE v11 deployment based on docker image ibmcom/ace:latest.  This manifest is also enabled for Prometheus Exporter integration.
    - To use this deployment run ./deploy_iib.sh
    - Insure to enable 'Monitor annotated Prometheus Exporters' on the Kubernetes settings page for Message Flow / Message Flow Node metrics.  
    - Currently requires manually loading sample ACE applications.  A sample 'CallHTTPSEcho.bar' file is located in the IIB Manifests folder.
       - Go to the published Service on port 7600, ie, http://{load balancer ip}:7600 and deploy the .bar file on each deployed instance
       - To access CallHTTPSEcho use port 7800, ie, http://{load balancer ip}:7800/CallHTTPSEcho
      
        
