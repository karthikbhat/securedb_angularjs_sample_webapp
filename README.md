# securedb_angularjs_sample_webapp

This repository shows a very simple webapp which integrates with **SecureDB RESTful Encrypted Identity Management APIs** via angularjs. The intention is to show how simple it is for anyone to come up with a fully integrated webapp providing enterprise class safe,secure, encrypted identity management within a matter of few hours using SecureDB APIs.

This web app can be deployed using Apache httpd or even deployed using Eclipse IDE.

# Following are the pre-requisites

## Getting your SecureDB user credentials
You need to register as a customer with SecureDB either via the cloud-service or via the on-premise offering to obtain your **Customer ID** and **Directory ID**. You can authenticate to SecureDB APIs in one of the two ways:

* Basic Authentication
* JSON Web Token (JWT)

Some of the APIs are also available without any authentication. Since angularjs runs within a browser, Basic Authentication will typically be never be used and is not the recommended way as well. The idea is to call "/authenticate" API and then use the JWT returned via that call to make further API calls. Based on the user being a regular or an admin user, different APIs will work. More on the APIs below.

## Important Files

There are three important files in this repository:

## js/sampleApp.js

This file contains all the angularjs code that integrates with various POST/PUT/GET/DELETE APIs that SecureDB provides. It basically defines a scope ($scope) in which all the variables are defined and get their values which are then used by various functions within this same scope to eventually make REST API calls
This $scope has two important variables which will be needed to be modified to get started.

#### $scope.customerId 

This will be set to the **Customer ID** obtained above. E.g:

$scope.customerId = "gJHyAMgv";

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

This file contains calls to all REST apis that can be invoked by admin and super-admin users. Examples about APIs like

* lock user
* add role
* get all users
* get account history of a specific user
* search for a specific user
* delete users

etc, can be found in this file. 

If you have any questions, please write to us at support at securedb.co
