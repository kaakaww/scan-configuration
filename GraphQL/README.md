# Scanning GraphQL API's with StackHawk

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

#### TL;DR
1. Create an application on the [StackHawk Web platform](https://auth.stackhawk.com/login).
2. Clone this repo or copy the `stackhawk-graphql.yml` configuration file and place in the root of your project directory.

## GraphQL Configuration

StackHawk is pioneering application security testing for GraphQL APIs. The scanner, Hawkscan, will perform introspection of a GraphQL app to generate routes based on available operations. The scanner can be configured to enumerate all available types and input parameters for Query and Mutation together, or for each individual type separately.

All [GraphQL configuration](https://docs.stackhawk.com/hawkscan/configuration#appgraphqlintrospection) settings can be viewed here.

For more help configuring GraphQL, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/openapi-configuration.html).

### Example Scan Configuration
```
app:
  applicationId: xxxxx-XXXX-xxx-XXXX-xxxxxxx # (required)
  env: Pre-Production # (required)
  host: http://localhost:3000 # (required)
  autoPolicy: true
  autoInputVectors: true
  graphqlConf:
    enabled: true
    schemaPath: /graphql
    operation: ALL # (default)
```

### Running the scanner

#### Bash
```bash
docker run --rm -v $(pwd):/hawk:rw -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-graphql.yml
```

#### Windows CLI
```bash
docker run --rm -v %cd%:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-graphql.yml
```

#### PowerShell
```PowerShell
docker run --rm -v ${PWD}:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-graphql.yml
```

#### Linux
```PowerShell
docker run --rm -v $(pwd):/hawk:rw -network host -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-graphql.yml
```
