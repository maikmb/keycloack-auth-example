# Keyclock service connect

This project demonstrates how to write a RESTful service with Node.js that is secured with <span>Keycloak</span>.

There are 3 endpoints exposed by the service:

* `public` - requires no authentication
* `secured` - can be invoked by users with the `user` role
* `admin` - can be invoked by users with the `admin` role

The endpoints are very simple and will only return a simple message stating what endpoint was invoked.


> Before you start: Make sure you have Docker installed.

## Setup Keycloak
From a terminal start Keycloak with the following command:

> docker run -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:18.0.2 start-dev

This will start Keycloak exposed on the local port 8080. It will also create an initial admin user with username admin and password admin.

## Login to the admin console
Go to the Keycloak Admin Console and login with the username and password you created earlier.

> Prior to running the project you need to create a realm and configure a client. For that: https://www.keycloak.org/getting-started/getting-started-docker

## Run project

1. Open a terminal and navigate to the root directory.

2. The following shows the command to run the project:

   ````
   npm install
   npm start
   ````

## Service Endpoints:

* public - <http://localhost:3000/service/public>
* secured - <http://localhost:3000/service/secured>
* admin - <http://localhost:3000/service/admin>

You can open the public endpoint directly in the browser to test the service. The two other endpoints require
invoking with a bearer token.