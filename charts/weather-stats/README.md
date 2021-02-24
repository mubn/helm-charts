# Weather Stats

"Weather Stats" is an all in one tool to gather and display atmospheric temperature-, humidity- and pressure data. The data can be collected for example with the [BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/). Boards with this sensor can be purchased in various online shops and operated with a Raspberry Pi for example. For mor information see the [project repository](https://github.com/mubn/weather-stats)

## Pre-requisites

[Helm](https://helm.sh/) needs to be installed.
You should create a tls certificate and set it in your helm values if you want to expose the app with an ingress.

## Installation

```
helm repo add mubn https://mubn.github.io/helm-charts/
helm repo update
helm install weather mubn/weather-stats -f myvalues.yaml
```

myvalues.yaml

```
app:
  username: test_user
  password: test_pass

ingress:
  enabled: true
  hosts:
    - host: weather.myhost.com
      paths:
        - /
  tls:
    - secretName: weather-myhost-tls
      hosts:
        - weather.myhost.com
```
