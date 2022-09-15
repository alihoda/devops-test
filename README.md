# devops-test

## Deployments

There are 5 deployments with their services and configMaps.

|Deployment|Service|ConfigMap|
|---|---|---|
|web-admin-deploy|web-admin-svc|web-admin-cm|
|web-customer-deploy|web-customer-svc|web-customer-cm|
|db-server-deploy|db-server-svc||
|phpmyadmin-deploy|phpmyadmin-svc||
|sip-server|||

> Although the *sip-server* is like *web-admin-deploy*, but not implemented. I could not recognize *sip-server* configuration in the *INSTALL.rst* file.

## ConfigMaps and Secrets

There three configMaps:

- *common-cm*: It is for common configuration like installing dependencies and creating directories.
- *web-admin-cm*: It is for *web-admin* gui configuration.
- *web-customer-cm*: It is for *web-customer* gui configuration.

And there is one Secret just to keep *user-pass* and *db-name*.

## Services

All Services are in the *default* namespace except *db-server-svc* and *phpmyadmin-svc* which there are in the *db-ns* namespace, because it is better to keep database related objects in separate namespace.

> Because the Ingress object needs to has access to *phpmyadmin-svc*, *phpmyadmin-svc* type is *ExternalName* with the FQDN.

---

## Notes

It seems you said **a sample Helm chart with a pipeline**, but I didn't have any idea to create a pipeline for a Helm chart yet, so there is no Helm chart and pipeline.

The *asterisk* was new for me and it was fun to work with it and k8s.

Thanks.
