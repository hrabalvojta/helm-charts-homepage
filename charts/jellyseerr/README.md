# jellyseerr

![Version: 2.1.0](https://img.shields.io/badge/Version-2.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.2.3](https://img.shields.io/badge/AppVersion-2.2.3-informational?style=flat-square)

jellyseerr helm chart for Kubernetes

**Homepage:** <https://github.com/Fallenbagel/jellyseerr>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Ludovic Ortega | <ludovic.ortega@adminafk.fr> |  |

## Source Code

* <https://github.com/M0NsTeRRR/helm-charts/tree/main/charts/jellyseerr>

## Requirements

Kubernetes: `>=1.23.0-0`

## Install
```console
helm install jellyseerr oci://ghcr.io/m0nsterrr/helm-charts/jellyseerr
```

Verify the signature with [cosign](https://docs.sigstore.dev/cosign/system_config/installation/) :
```console
cosign verify ghcr.io/m0nsterrr/helm-charts/jellyseerr:2.1.0 --certificate-identity=https://github.com/M0NsTeRRR/helm-charts/.github/workflows/releases.yml@refs/heads/main --certificate-oidc-issuer=https://token.ac
tions.githubusercontent.com
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| config | object | `{"persistence":{"accessModes":["ReadWriteOnce"],"annotations":{},"name":"","size":"5Gi","volumeName":""}}` | Creating PVC to store configuration |
| config.persistence.accessModes | list | `["ReadWriteOnce"]` | Access modes of persistent disk |
| config.persistence.annotations | object | `{}` | Annotations for PVCs |
| config.persistence.name | string | `""` | Config name |
| config.persistence.size | string | `"5Gi"` | Size of persistent disk |
| config.persistence.volumeName | string | `""` | Name of the permanent volume to reference in the claim. Can be used to bind to existing volumes. |
| extraEnv | list | `[]` | Environment variables to add to the jellyseerr pods |
| extraEnvFrom | list | `[]` | Environment variables from secrets or configmaps to add to the jellyseerr pods |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.registry | string | `"docker.io"` |  |
| image.repository | string | `"fallenbagel/jellyseerr"` |  |
| image.sha | string | `""` |  |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.ingressClassName | string | `""` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.automount | bool | `true` | Automatically mount a ServiceAccount's API credentials? |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| strategy | object | `{"type":"Recreate"}` | Deployment strategy |
| tolerations | list | `[]` |  |