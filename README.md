### Product Catalog Basic GitOps Example

This is a basic example of deploying an application via OpenShift GitOps (i.e. Argo CD).

### Instructions

You can either deploy the application directly or via GitOps. To deploy this application directly to OpenShift with kustomize using the following command:

```
oc apply -k clusters/<YOUR-CLUSTER>/overlays/basic
```

To deploy it in OpenSshift GitOps first install the operator, the easiest way is to use the [https://github.com/gnunn-gitops/gitops-operator-install](gitops-operator-install) repo which will confirm everything for you. Alternatively you can install it manually via the console as well in Operator Hub.

Once you have the operator, simply create a new application as per the image below:

![alt text](https://raw.githubusercontent.com/gnunn-gitops/product-catalog-basic/master/docs/images/argocd-create-app.png)

Note the git path should be `environments/overlays/basic`.
