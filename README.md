# What is CX Cloud?

CX Cloud is an idea for creating scalable microservices based architecture on AWS. This project is created and maintained by [TietoEvry CX](https://www.tietoevry.com/en/services/digital-experience/customer-experience/) practice. We use this idea, accelerators, architecture and 3rd party tools \(e.g. commercetools, Algolia, Contentful\) for creating high quality digital services for our customers.

For more information, please head over to the [CX Cloud documentation](https://docs.cxcloud.com/).

## Helm chart repository

Add the CX Cloud Helm chart repository with the following command:

```bash
helm repo add cxcloud https://cxcloud.github.io/helm-charts
```

Keep the repository updated with:

```bash
helm repo update
```

## Publish new packages

Make sure that the Helm chart changes has been done and that the Chart.yaml file is updated in the Helm chart repository to publish.

In this example we'll use helm-deploy-service that has been cloned locally to `../cxcloud-deployment-chart`.

Create the package with

```bash
helm package ../cxcloud-deployment-chart
```

Update the index file with

```bash
helm repo index . --merge index.yaml --url https://github.com/cxcloud/helm-charts/raw/master
```

Commit and push the changes. Make sure to update the repo with `helm repo update`

*Happy Helming!*

## About Releases

| Version | Description |
| --- | --- |
| 0.2.1 | Fixed Ingress for v1 |
| 0.2.0 | Ingress apiVersion networking.k8s.io/v1. Requires Kubernetes 1.19 |
| 0.1.6 | WAFv2 support |
| 0.1.5 | Assign service account to deployment|
| 0.1.4 | Adding Security Context |
| 0.1.3 | create service account |
| ... | ... |

## License

CX Cloud and its components are released under the MIT license.
