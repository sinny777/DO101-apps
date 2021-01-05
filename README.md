# DO101-apps

Apps for the DO101 course.

# Project setup

## Pre-requisites

npm install -g express
npm install -g express-generator


### Free Weather API Key

https://home.openweathermap.org/api_keys

## Generate basic package structure and files

express $pwd

npm install

## Start application

DEBUG=myapp:* npm start


## Openshift

oc login https://api.ap45.prod.nextcle.com:6443

## Openshift Deploy App

oc new-project gurvsin3-scale

oc new-app --name version https://github.com/sinny777/DO101-apps#update-app --context-dir version

https://github.com/sinny777/DO101-apps.git

oc expose svc/version

## Routes configuration

    haproxy.router.openshift.io/balance: roundrobin
    haproxy.router.openshift.io/disable_cookies: 'true'

## Auto Scaling

oc project gurvsin3-scale

oc autoscale deployment scale --max=3 --cpu-percent=20