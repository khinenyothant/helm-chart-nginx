# My Helm Chart

This Helm chart deploys a sample nginx application.



## Default Values

The following is the default `values.yaml` file for this Helm chart:

```yaml
# Default values for my-chart.
# Declare variables to be passed into your templates.
name: nginx-sample
replicaCount: 3

labels:
  app: nginx-sample-app

selectorLabels:
  app: nginx-sample
  version: v1

service:
  type: ClusterIP
  port: 80
  targetPort: http
  protocol: TCP
  name: http

autoscaling:
  enabled: true
  replicaCount: 1

------

Customization
You can customize the chart by providing a custom values.yaml file. For example, to deploy with a different name, create a my-custom-values.yaml file with the following content:

```bash
helm install my-release myrepo/kntchart -f my-custom-values.yaml
