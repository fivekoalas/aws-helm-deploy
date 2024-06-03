# AWS HELM DEPLOY

A GitHub Action to deploy a ECR Helm chart to an AWS EKS cluster.

## Usage

Add the following step to your workflow:

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      id-token: write
      contents: read
    steps:
      - uses: fivekoalas/aws-helm-deploy@v1
        with:
          aws-region: "us-east-1"
          aws-account-id: "123456789012"
          aws-role-name-to-assume: "RoleName"
          chart-name: "my-chart"
          chart-version: "1.0.0"
          cluster-name: "my-cluster"
          cluster-region: "us-east-1" # Optional, defaults to aws-region
          helm-ecr-account-id: "123456789012"
          helm-ecr-region: "us-east-1" # Optional, defaults to aws-region
          helm-release-name: "my-release"
          image-tag: "latest"
          namespace: "default"
          values: values.yaml
```

## License Summary

This code is made available under the MIT license.
