# kubezero-cert-manager

![Version: 0.4.0](https://img.shields.io/badge/Version-0.4.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

KubeZero Umbrella Chart for cert-manager

**Homepage:** <https://kubezero.com>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Quarky9 |  |  |

## Requirements

Kubernetes: `>= 1.16.0`

| Repository | Name | Version |
|------------|------|---------|
| https://charts.jetstack.io | cert-manager | 1.0.3 |
| https://zero-down-time.github.io/kubezero/ | kubezero-lib | >= 0.1.3 |

## AWS - IAM Role
If you use kiam or kube2iam and restrict access on nodes running cert-manager please adjust:
```
cert-manager.podAnnotations:
  iam.amazonaws.com/role: <ROLE>
```

## Resolver Secrets
If your resolvers need additional sercrets like CloudFlare API tokens etc. make sure to provide these secrets separatly matching your defined issuers.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cert-manager.cainjector.nodeSelector."node-role.kubernetes.io/master" | string | `""` |  |
| cert-manager.cainjector.tolerations[0].effect | string | `"NoSchedule"` |  |
| cert-manager.cainjector.tolerations[0].key | string | `"node-role.kubernetes.io/master"` |  |
| cert-manager.extraArgs[0] | string | `"--dns01-recursive-nameservers-only"` |  |
| cert-manager.ingressShim.defaultIssuerKind | string | `"ClusterIssuer"` |  |
| cert-manager.ingressShim.defaultIssuerName | string | `"letsencrypt-dns-prod"` |  |
| cert-manager.installCRDs | bool | `true` |  |
| cert-manager.nodeSelector."node-role.kubernetes.io/master" | string | `""` |  |
| cert-manager.podAnnotations | object | `{}` | "iam.amazonaws.com/roleIAM:" role ARN the cert-manager might use via kiam eg."arn:aws:iam::123456789012:role/certManagerRoleArn" |
| cert-manager.prometheus.servicemonitor.enabled | bool | `false` |  |
| cert-manager.tolerations[0].effect | string | `"NoSchedule"` |  |
| cert-manager.tolerations[0].key | string | `"node-role.kubernetes.io/master"` |  |
| cert-manager.webhook.nodeSelector."node-role.kubernetes.io/master" | string | `""` |  |
| cert-manager.webhook.tolerations[0].effect | string | `"NoSchedule"` |  |
| cert-manager.webhook.tolerations[0].key | string | `"node-role.kubernetes.io/master"` |  |
| clusterIssuer | object | `{}` |  |
| localCA.enabled | bool | `true` |  |
| localCA.selfsigning | bool | `true` |  |
