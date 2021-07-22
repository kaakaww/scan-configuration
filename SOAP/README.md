# Scanning SOAP API's with StackHawk

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

#### TL;DR
1. Create an application on the [StackHawk Web platform](https://auth.stackhawk.com/login).
2. Clone this repo or copy the `stackhawk-soap.yml` configuration file and place in the root of your project directory.


## SOAP API configuration

SOAP API schemas use XML to define the structure of its operations. The schema is made available through a WSDL file, offering a machine-readable format for how the web service works.

HawkScan will use the contents provided by the WSDL to improve the quality of the scan by:

* Pre-seeding the sitemap using the routes defined in the WSDL. This can be used to complement any crawled routes or can be used instead of app spidering altogether.
* Using defined inputs to operations in the spec to inform how to communicate with the web application and gather clues on how to better attack endpoints.

### Configuration Examples

| Using a spec file                                                   | Using a relative URL                                                                                        |
| :------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------- |
| app:<br />&nbsp;&nbsp;...<br />&nbsp;&nbsp;soapConf: "soapAPI.wsdl" | app:<br />&nbsp;&nbsp;...<br/>&nbsp;&nbsp;soapConf: /soapAPI/v1?wsdl                                        |

### Example Scan Configuration
```
app:
  applicationId: xxxx-XXXX-xxxx-XXXX-xxxxxxxx
  env: Development
  host: http://localhost:8000
  autoPolicy: true
  api: /soapAPI/v1?wsdl]
```

For more help configuring SOAP API's, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/soap-configuration.html).
