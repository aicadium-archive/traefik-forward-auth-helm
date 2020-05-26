# traefik-forward-auth

Helm chart for [traefik-forward-auth](https://github.com/thomseddon/traefik-forward-auth)

## Requirements

* [Helm](https://helm.sh/) >=3.0.0
* Kubernetes >=1.8

## Usage notes and getting started

* Populate values.yaml with appropriate values in `forward_auth_config.***`

## Installing

### Using the Helm repository

- Add the Elastic Helm charts repo: `helm repo add traefik-forward-auth https://basisai.github.io/traefik-forward-auth-helm`
- Install it: `helm install traefik-forward-auth traefik-forward-auth/traefik-forward-auth`

### Using the master branch

- Clone the git repo: `git clone git@github.com:basisai/traefik-forward-auth-helm.git`
- Install it: `helm install traefik-forward-auth traefik-forward-auth/`

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `3` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| forward_auth_config.client_id | string | `"fixme"` |  |
| forward_auth_config.client_secret | string | `""` |  |
| forward_auth_config.cookie_domain | string | `"example.bdrk.ai"` |  |
| forward_auth_config.insecure_cookie | bool | `false` |  |
| forward_auth_config.issuer_url | string | `"https://example.auth0.com/"` |  |
| forward_auth_config.lifetime | int | `36000` |  |
| forward_auth_config.prompt | string | `""` |  |
| forward_auth_config.provider | string | `"oidc"` |  |
| forward_auth_config.secret | string | `""` |  |
| forward_auth_config.url_path | string | `"/_oauth"` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"thomseddon/traefik-forward-auth"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations."ingress.kubernetes.io/content-type-nosniff" | string | `"true"` |  |
| ingress.annotations."ingress.kubernetes.io/force-hsts" | string | `"true"` |  |
| ingress.annotations."ingress.kubernetes.io/frame-deny" | string | `"true"` |  |
| ingress.annotations."ingress.kubernetes.io/hsts-max-age" | string | `"315360000"` |  |
| ingress.annotations."ingress.kubernetes.io/protocol" | string | `"http"` |  |
| ingress.annotations."ingress.kubernetes.io/referrer-policy" | string | `"strict-origin"` |  |
| ingress.annotations."kubernetes.io/ingress.class" | string | `"traefik"` |  |
| ingress.annotations."traefik.ingress.kubernetes.io/preserve-host" | string | `"true"` |  |
| ingress.enabled | bool | `false` |  |
| ingress.host | string | `"auth.example.bdrk.ai"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podDisruptionBudget.minAvailable | int | `1` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.annotations | object | `{}` |  |
| service.labels | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |
