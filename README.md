# traefik-forward-auth

Helm chart for [traefik-forward-auth](https://github.com/thomseddon/traefik-forward-auth)

Traefik Forward Auth provides login and authentication for the Traefik reverse proxy. It is expected to work with the [Authorization Code Flow](https://auth0.com/docs/flows/concepts/auth-code).

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
| forward_auth_config.log_format | string | `"text"` |  |
| forward_auth_config.log_level | string | `"info"` |  |
| forward_auth_config.prompt | string | `""` |  |
| forward_auth_config.provider | string | `"oidc"` |  |
| forward_auth_config.secret | string | `""` |  |
| forward_auth_config.url_path | string | `"/_oauth"` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"thomseddon/traefik-forward-auth"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations."ingress.kubernetes.io/auth-response-headers" | string | `"X-Forwarded-User"` |  |
| ingress.annotations."ingress.kubernetes.io/auth-type" | string | `"forward"` |  |
| ingress.annotations."ingress.kubernetes.io/auth-url" | string | `"http://traefik-forward-auth"` |  |
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
| podSecurityPolicies.annotations."apparmor.security.beta.kubernetes.io/allowedProfileNames" | string | `"runtime/default"` |  |
| podSecurityPolicies.annotations."apparmor.security.beta.kubernetes.io/defaultProfileName" | string | `"runtime/default"` |  |
| podSecurityPolicies.annotations."seccomp.security.alpha.kubernetes.io/allowedProfileNames" | string | `"docker/default,runtime/default"` |  |
| podSecurityPolicies.annotations."seccomp.security.alpha.kubernetes.io/defaultProfileName" | string | `"runtime/default"` |  |
| podSecurityPolicies.labels | object | `{}` |  |
| podSecurityPolicies.spec.allowPrivilegeEscalation | bool | `false` |  |
| podSecurityPolicies.spec.forbiddenSysctls[0] | string | `"*"` |  |
| podSecurityPolicies.spec.fsGroup.ranges[0].max | int | `65535` |  |
| podSecurityPolicies.spec.fsGroup.ranges[0].min | int | `1` |  |
| podSecurityPolicies.spec.fsGroup.rule | string | `"MustRunAs"` |  |
| podSecurityPolicies.spec.hostIPC | bool | `false` |  |
| podSecurityPolicies.spec.hostNetwork | bool | `false` |  |
| podSecurityPolicies.spec.hostPID | bool | `false` |  |
| podSecurityPolicies.spec.privileged | bool | `false` |  |
| podSecurityPolicies.spec.readOnlyRootFilesystem | bool | `true` |  |
| podSecurityPolicies.spec.runAsGroup.ranges[0].max | int | `65535` |  |
| podSecurityPolicies.spec.runAsGroup.ranges[0].min | int | `1` |  |
| podSecurityPolicies.spec.runAsGroup.rule | string | `"MustRunAs"` |  |
| podSecurityPolicies.spec.runAsUser.ranges[0].max | int | `65535` |  |
| podSecurityPolicies.spec.runAsUser.ranges[0].min | int | `1` |  |
| podSecurityPolicies.spec.runAsUser.rule | string | `"MustRunAs"` |  |
| podSecurityPolicies.spec.seLinux.rule | string | `"RunAsAny"` |  |
| podSecurityPolicies.spec.supplementalGroups.ranges[0].max | int | `65535` |  |
| podSecurityPolicies.spec.supplementalGroups.ranges[0].min | int | `1` |  |
| podSecurityPolicies.spec.supplementalGroups.rule | string | `"MustRunAs"` |  |
| podSecurityPolicies.spec.volumes[0] | string | `"configMap"` |  |
| podSecurityPolicies.spec.volumes[1] | string | `"emptyDir"` |  |
| podSecurityPolicies.spec.volumes[2] | string | `"projected"` |  |
| podSecurityPolicies.spec.volumes[3] | string | `"secret"` |  |
| podSecurityPolicies.spec.volumes[4] | string | `"downwardAPI"` |  |
| priorityClassName | string | `""` |  |
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
