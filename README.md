# eda-catalog
A repo of apps for Nokia's Event Driven Automation orchestration platform.

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
