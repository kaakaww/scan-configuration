# Scanning REST API's with StackHawk

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

#### TL;DR
1. Create an application on the [StackHawk Web platform](https://auth.stackhawk.com/login).
2. Clone this repo or copy the `stackhawk-rest.yml` configuration file and place in the root of your project directory.

## OpenAPI Configuration

The [OpenAPI Specification](https://swagger.io/specification/) (AKA Swagger) is an industry-adopted standard for describing RESTful interfaces, which HawkScan can use to deliver a faster, more thorough scan.

HawkScan will use the contents of a provided OpenAPI spec to improve the quality of the scan by:

* Pre-seeding the sitemap using the routes defined in the OpenAPI spec. This can be used to complement any crawled routes or can be used instead of app spidering altogether.
* Using defined inputs to routes in the spec to inform how to communicate with the web application and gather clues on how to better attack endpoints.

HawkScan can work with OpenAPI definitions as separate files or defined inline via the stackhawk.yml.

For more help configuring OpenAPI, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/openapi-configuration.html).

### Configuration Examples

| Using a spec file                                                                                             | Using a relative URL                                                                                  |
| :------------------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------- |
| app:<br />&nbsp;&nbsp;...<br />&nbsp;&nbsp;openApiConf:<br />&nbsp;&nbsp;&nbsp;&nbsp;filePath: "openapi.yaml" | app:<br />&nbsp;&nbsp;...<br/>&nbsp;&nbsp;openApiConf:<br />&nbsp;&nbsp;&nbsp;&nbsp;path: /api/docs   |

### Example Scan Configuration
```
app:
  applicationId: xxxx-XXXX-xxxx-XXXX-xxxxxxxx
  env: Development
  host: http://localhost:8000
  autoPolicy: true
  openApiConf:
    path: /swagger
```
