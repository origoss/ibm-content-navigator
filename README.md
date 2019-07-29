# IBM Content Navigator (ICN)

## Prerequisites Details
- [IBM Content Platform Engine](https://github.com/origoss/ibm-content-platform-engine)

## Chart Details
IBM® Content Navigator is a web client that can connect to multiple IBM Content Manager Enterprise Edition, IBM Content Manager OnDemand, and IBM FileNet® P8 repositories.
ref.: [IBM](https://www.ibm.com/support/knowledgecenter/en/SSEUEX_3.0.4/com.ibm.installingeuc.doc/eucao002.htm)

## Installing the Chart
This chart uses config files to establish connection with a global database and a ldap-service for authentication. Sample config files are located in ./config-samples folder. Edit sample files then copies to config folder.

To install the chart with the release name `my-release`:
```bash
{
    #!/bin/bash
    set -ex

    [[ -d configs ]] || mkdir configs
    cp configs-samples/ICNDS.xml.sample configs/ICNDS.xml
    cp configs-samples/JCCDriver.xml.sample configs/JCCDriver.xml
    cp configs-samples/ldap.xml.sample configs/ldap.xml

    helm install ./ --name my-release
}
```

## Deleting the Charts

Delete the Helm deployment as normal:

```
$ helm delete my-release
```