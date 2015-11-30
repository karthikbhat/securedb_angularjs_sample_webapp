# securedb_angularjs_sample_webapp

This sample AngularJS webapp shows you how to integrate with [**SecureDB RESTful Encrypted Identity Management APIs**](https://securedb.co) using AngularJS. The intention is to show how simple it is for anyone to come up with a fully integrated webapp providing enterprise class safe,secure, encrypted identity management within a matter of few hours using SecureDB APIs.

This web app can be deployed using Apache httpd or even deployed using Eclipse IDE.

# Following are the pre-requisites

## Getting your SecureDB user credentials
SecureDB Encrypted IdM is available as a cloud service (aka SecureDB Cloud) or as an on-premise (aka SecureDB Enterprise) service. You can can create a FREE account on our SecureDB Cloud service (See [Quick Start Guide](https://securedb.co/docs/#quick-start) to get started). Once you register as a customer with SecureDB (either via the cloud-service or via the on-premise offering), you will get your **Customer ID** and **Directory ID**. 

You can authenticate to SecureDB APIs in one of the two ways:

* Basic Authentication (BA)
* JSON Web Token (JWT)

Some of the APIs are also available without any authentication. Since AngularJS runs within a browser, BA should not be used to authenticate to the APIs. This is to avoid storing the BA header values at the browser. Hence, all the APIs used in this sample webapp use only JWT to authenticate to SecureDB Encrypted IdM APIs. The APIs that require BA for authentication are not included in this sample web app. So, the idea is to call "/authenticate" API first, and then use the JWT returned to make further API calls. Based on the authenticated user being a regular or a SecureDB Admin user, different APIs will work. More on the APIs below.

## Important Files

There are three important files in this repository:

## js/sampleApp.js

This file contains all the AngularJS code that integrates with various POST/PUT/GET/DELETE APIs that SecureDB Encrypted IdM provides. It basically defines a scope ($scope) in which all the variables are defined and get their values which are then used by various functions within this same scope to eventually make REST API calls
This $scope has two important variables which will be needed to be modified to get started.

#### $scope.customerId 

This will be set to the **Customer ID** obtained above. E.g:

$scope.customerId = "gDyUAMgv";

#### $scope.directoryId

This will be set to the **Directory ID** obtained above. E.g:

$scope.directoryId = "angularjs_test";

## user.html

This file contains calls to all REST apis that can be invoked by regular non-admin users. So examples about APIs like

* authenticate
* change password
* create basic profile
* update basic profile

etc, can be found in this file.

## admin.html

This file contains calls to all REST apis that can be invoked by SecureDB admin and super-admin users. Examples about APIs like

* lock user
* add role
* get all users
* get account history of a specific user
* search for a specific user
* delete users

etc, can be found in this file. 

# Further Read
[SecureDB API Reference Guide](https://securedb.co/apidocs)
[SecureDB API Playground (Swagger)](https://api.securedb.co/)
[SecureDB Documentation](https://securedb.co/docs)

If you have any questions, please write to us at support at securedb.co
