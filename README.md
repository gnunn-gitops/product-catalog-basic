### Product Catalog Basic GitOps Example

This is a basic example of deploying an application via OpenShift GitOps (i.e. Argo CD).

### Instructions

You will need to clone this repo and add a new clusters in the `/clusters` directory, easiest way is to simply copy an existing one like `local.home` including the subdirectories and files. Once copied, edit the file `patch.yaml` and update the two wildcards to match your domain wildcard.

In other changes, if you copied `local.home` change the wildcard `apps.home.ocplab.com` in the two URLS to your OpenShift's wildcard domain

Once this is done, you can either deploy the application directly or via GitOps. To deploy this application directly to OpenShift with kustomize using the following command:

```
oc apply -k clusters/<YOUR-CLUSTER>/overlays/basic
```

To deploy it in OpenSshift GitOps first install the operator, the easiest way is to use the [https://github.com/gnunn-gitops/gitops-operator-install](gitops-operator-install) repo which will confirm everything for you. Alternatively you can install it manually via the console as well in Operator Hub.

Once you have the operator, simply create a new application as per the image below:

![alt text](https://raw.githubusercontent.com/gnunn-gitops/product-catalog-basic/master/docs/images/argocd-create-app.png)

Make sure to change the cluster name, `aws.cluster`, in the path to your cluster name.
