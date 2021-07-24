# External Token Authentication

Sometimes authentication is not performed with just a `username` and `password`. For example, API key access or third-party authentication services like OAuth require custom tokens.

To support this type of authentication, HawkScan supports externally supplying an authorization token with the authentication.external configuration.

The external supplied authorization token can be used in conjunction with either `cookieAuthorization` or `tokenAuthorization`. This scenario will use `tokenAuthorization`, a custom header for the authorization token and pass an externally generated token from our web application’s JWT library. This will allow us to run HawkScan as any user of our application in a programatic fashion.

For more help configuring External Token Authentidation, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/authenticated-scanning.html#external-token-authentication--custom-token-authorization)

#### Running the scanner with multiiple config files
To better support advanced configurations you can provide multiple configuration files as an overlay to the base scan configuration `stackhawk.yml`. Subsequent configuration files will be merged on top of the prior, effectively replacing any duplicate setting values form the previous scan configuration file.

```
docker run --name hawkscan --network host -e API_KEY=${API_KEY} --rm -v $(pwd):/hawk:rw -t stackhawk/hawkscan:latest stackhawk-graphql.yml stackhawk-cookie.yml
```
