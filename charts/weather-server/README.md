# Weather Stats

"Weather Server" is an app to collect, store and distribute weather data. Data from multiple sensors can be transmitted in a very flexible JSON format. All entries will be saved in a Mongo database. For more information see the [project repository](https://github.com/mubn/weather-server)

## Pre-requisites

A MongoDB server should exist. [Helm](https://helm.sh/) needs to be installed. An OAuth 2 authorization provider (like Auth0) API endpoint should be configured.

## Installation

```
helm repo add mubn https://mubn.github.io/helm-charts/
helm repo update
helm install weather mubn/weather-server -f myvalues.yaml
```

Mandatory entries in the myvalues.yaml:

```
app:
  database: mongodb://my-mongo-host:27017/weatherData
  authDomain: mydomain.auth0.com
  authAudience: https://my-weather-app
  appDomain: mydomain.weather.app
  
```
