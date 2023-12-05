# Scrypted Helm Chart

## Example usage

```bash
helm upgrade --install my-cameras scrypted -f myvalues.yaml
```

```yaml
# myvalues.yaml
image:
  repository: koush/scrypted
  tag: latest
  pullPolicy: Always

env:
  securePort: 9443
  insecurePort: 11080
  timezone: "America/Detroit"

service:
  type: ClusterIP
  port: 11080
  securePort: 9443

hostNetwork: true

nodeAffinity:
  requiredDuringSchedulingIgnoredDuringExecution:
    nodeSelectorTerms:
    - matchExpressions:
      - key: smarthome
        operator: In
        values:
        - scrypted

ingress:
  enabled: true
  hosts:
    - host: scrypted.mylocaldomain.org
      paths: ["/"]

persistence:
  enabled: true
  storageClass: "longhorn"
  accessMode: ReadWriteMany
  size: 1Gi
```
