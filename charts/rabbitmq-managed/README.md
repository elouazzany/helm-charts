# rabbitmq-managed

![Version: 0.4.1](https://img.shields.io/badge/Version-0.4.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 3.10](https://img.shields.io/badge/AppVersion-3.10-informational?style=flat-square)

A Helm chart to manage RabbitmqCluster & typology

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.className | string | `nil` |  |
| ingress.annotations | object | `{}` |  |
| ingress.labels | object | `{}` |  |
| ingress.host | string | `"example.test"` | Define the hostname to use. |
| ingress.tls.enabled | bool | `true` | Enable TLS, with a default secret reference |
| ingress.tls.customSecretName | string | `""` | Specify an existing secret if not automatically provisionned |
| cluster.replicaCount | int | `3` | Configure number of rabbitmq replicas (should be an odd numbers) |
| cluster.image | string | `""` | Specify an image to use if different from operator default |
| cluster.rabbitmqConf | object | `{}` | Inject rabbitmq conf, which are under RabbitmqCluster.spec.rabbitmq |
| cluster.override | object | `{}` | Set value to override the templated statefulset by the operator |
| cluster.resources.limits | object | `{}` | Define rabbitmq cluster container limits. |
| cluster.resources.requests | object | `{}` | Define rabbitmq cluster container requests. |
| cluster.extraSpec | object | `{}` | Inject values directly into .spec of RabbitmqCluster manifests |
| vhosts | list | `[]` | The default vhost (`/`) is automatically created |
| users | list | `[]` | Define the list of users, assigned vhosts and corresponding permissions |
| policies | list | `[]` | Create rabbitmq policy to apply automatically |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.8.1](https://github.com/norwoodj/helm-docs/releases/v1.8.1)
