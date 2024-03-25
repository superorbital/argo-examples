## Argo Installation for Fastly Next-Gen WAF Product

These Argo applications represent the current state for installing the product
in different configurations.

- [NGINX Install Argo App](./ingress-nginx.yaml)
- [Istio Authorization Policy Argo](./istio-auth.yaml)

### Dependencies

In order to install these Argo applications, you must set up the following dependencies:

- [ArgoCD](https://argo-cd.readthedocs.io/en/stable/operator-manual/installation/)
- [External Secrets Operator (ESO)](https://external-secrets.io/latest/introduction/getting-started/)

External secrets operator can be synced as an Argo application.

Override the `external-secret.yaml` provided in this repository with your own external secrets implementation
depending on [your secret provider](https://external-secrets.io/latest/provider/aws-secrets-manager/).

### Installing

Install the desired Argo application to your cluster and ensure healthy sync. The Next-Gen WAF is installed
in the `application` namespace in these examples.

```console
kubectl apply -f ingress-nginx.yaml
```