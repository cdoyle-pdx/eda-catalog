# eda-catalog
A repo of apps for Nokia's Event Driven Automation orchestration platform.

apiVersion: appstore.eda.nokia.com/v1  
kind: Catalog  
metadata:  
&emsp;&emsp;name: cdoyle-pdx  
&emsp;&emsp;namespace: eda-system  
spec:  
&emsp;&emsp;enabled: true  
&emsp;&emsp;refreshInterval: 180  
&emsp;&emsp;remoteType: git  
&emsp;&emsp;remoteURL: https://github.com/cdoyle-pdx/eda-catalog  
&emsp;&emsp;skipTLSVerify: false  
&emsp;&emsp;title: cdoyle-pdx EDA Apps
