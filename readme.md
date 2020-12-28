# Serverless Plugin: serverless-api-client-certificate
Serverless framework currently doesn't provide a way to manage client certificates on Rest Api stages. 

This plugin will check the deployed api stage for the existence of a client certificate. 

If certificate exists and has not expired, it simply displays the current expiration date, otherwise, if configured to rotate to a new certificate, it will create and assign a new one. If the Api stage is not assigned to a certificate, then one will be created and assigned to the Api stage.

To configure, add a custom configuration section:
```
plugins:
  - serverless-api-client-certificate

custom:
  serverlessApiClientCertificate:
    rotateCerts: true
    daysLeft: 30
```
* The 'rotateCerts' parameter will determine whether to auto-rotate the certificate
* The 'daysLeft' parameter will determine how many days are left until expiration before rotating a new certificate.

