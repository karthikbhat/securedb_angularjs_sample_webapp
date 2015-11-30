# securedb_angurlarjs_webapp

This repository shows a very simple webapp which integrates with **SecureDB RESTful Encrypted Identity Management APIs** via angularjs. The intention is to show how simple it is for anyone to come up with a fully integrated webapp providing enterprise class safe,secure, encrypted identity management within a matter of few hours using SecureDB APIs.

This web app can be deployed using Apache httpd or even deployed using Eclipse IDE.

# Following are the pre-requisites

## Getting your SecureDB user credentials
You need to register as a customer with SecureDB either via the cloud-service or via the on-premise offering to obtain your **Customer ID** and **Directory ID**.

## Important Files

There are three important files in this repository:

1. js/sampleApp.js
This file contains all the angularjs code that integrates with various POST/PUT/GET/DELETE APIs that SecureDB provides. It basically defines a scope ($scope) in which all the variables are defined and get their values which are then used by various functions within this same scope to eventually make REST API calls
This $scope has two important variables which will be needed to be modified to get started.

### $scope.customerId 
This will be set to the **Customer ID** obtained above. E.g:
$scope.customerId = "gJHyAMgv";

### $scope.directoryId
This will be set to the **Directory ID** obtained above
$scope.directoryId = "angularjs_test";

