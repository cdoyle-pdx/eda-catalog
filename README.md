# Event Driven Arcade
Arcade games for Nokia's Event Driven Automation (EDA) platform, played right in the EDA UI.

| App | Description |
|---|---|
| Snake | Nokia Snake — the arena is drawn from your live fabric topology |
| Polybius | A weird game I ripped from an old ROM board found in the basement of a PDX Arcade |

Use the code below to connect your EDA cluster to the Event Driven Arcade catalog.

```
apiVersion: appstore.eda.nokia.com/v1
kind: Catalog
metadata:
  name: event-driven-arcade
  namespace: eda-system
spec:
  enabled: true
  refreshInterval: 180
  remoteType: git
  remoteURL: https://github.com/cdoyle-pdx/event-driven-arcade
  skipTLSVerify: false
  title: Event Driven Arcade
```

Create a file named signingkey.yaml and paste the following code into it.
```
apiVersion: appstore.eda.nokia.com/v1
kind: SigningKey
metadata:
  name: cdoyle-pdx
  namespace: eda-system
spec:
  publicKeys:
    - title: cdoyle-pdx
      key: |
        -----BEGIN PUBLIC KEY-----
        MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEPZSsQ0ijU5UImxzLTGodpismNNoJ
        4xCilwUET5mHvR9Q21vczm040Dn9VITMed47v3waPWlwz+YVba2ij5idjA==
        -----END PUBLIC KEY-----
```
On your EDA server, install the public key YAML file so you don't get app installation cert errors!
```
kubectl apply -f signingkey.yaml
kubectl get signingkeys -A
```

