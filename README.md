# Homelab Helm Charts

Collection of Helm Charts I support for my homelab.

## [Scrypted](./charts/scrypted)

[Scrypted](https://scrypted.app) can bridge most cameras to the three major home hubs: HomeKit (including HomeKit Secure Video), Google Home, and Alexa. Scrypted streams are fast, low latency, and have rock solid reliability.

```bash
helm repo add scrypted https://charts.chriskirby.net/scrypted
# deploy to your cluster
helm upgrade --install cameras scrypted
```
