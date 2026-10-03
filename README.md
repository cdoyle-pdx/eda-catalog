# eda-catalog
A repo of apps for Nokia's Event Driven Automation orchestration platform.

Use the code below to connect your EDA cluster to my catelog.

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
        MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEOPyd97Sd7SU9SybQkBfnA7fMc1Ib
        BMrdNVTrLuunRV2tqo/a83Wh1vJ+qkAwRpfUYeZq88EveiOUUmVg0u/6sQ==
        -----END PUBLIC KEY-----
```
On your EDA server, install the public key YAML file so you don't get app installation cert errors!
```
kubectl apply -f signingkey.yaml
kubectl get signingkeys -A
```
