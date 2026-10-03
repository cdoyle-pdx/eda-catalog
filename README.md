# eda-catalog
A repo of apps for Nokia's Event Driven Automation orchestration platform.

```
apiVersion: appstore.eda.nokia.com/v1
kind: Catalog
metadata:
  name: cdoyle-pdx
  namespace: eda-system
spec:
  enabled: true
  refreshInterval: 180
  remoteType: git
  remoteURL: https://github.com/cdoyle-pdx/eda-catalog
  skipTLSVerify: false
  title: cdoyle-pdx EDA Apps
```
Create a YAML file named signingkey.yaml
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
        MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEOPyd97Sd7SU9SybQkBfnA7fMc1Ib
        BMrdNVTrLuunRV2tqo/a83Wh1vJ+qkAwRpfUYeZq88EveiOUUmVg0u/6sQ==
        -----END PUBLIC KEY-----
```
Load it into EDA
```
kubectl apply -f signingkey.yaml
kubectl get signingkeys -A
```
