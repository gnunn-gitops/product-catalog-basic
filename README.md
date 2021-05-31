### Product Catalog Basic GitOps Example

This is a basic example of deploying an application via OpenShift GitOps (i.e. Argo CD).

### Instructions

You will need to clone this repo and add a new clusters in the `/clusters` directory, easiest way is to simply copy an existing one like `local.home` including the subdirectories and files. Once copied, edit the file `patch.yaml` and update the two wildcards to match your domain wildcard.

In other changes, if you copied `local.home` change the wildcard `apps.home.ocplab.com` in the two URLS to your OpenShift's wildcard domain

Once this is done, you can then deploy this application manually to OpenShift with kustomize using the following command:

```
oc apply -k clusters/<YOUR-CLUSTER>/overlays/basic
```

To add it in OpenSshift GitOps first install the operator.
