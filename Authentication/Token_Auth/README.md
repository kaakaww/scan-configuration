# Token Authentication

Many modern web application backends are APIs that serve data to more than just html based web browsers. These apps do not rely on web forms for authentication. This approach is common for single page applications that use modern javascript frameworks like Angular, React, Vue.js, and others.

A common approach for authentication in this scenario is to create an API route that accepts a user’s credentials via a `POST` request of `JSON` data with the request returning an Authorization token as part of the `JSON` response payload. The API then expects the token be sent on all subsequent requests to protected API routes as an Authorization header. This method of authorization is commonly referred to as bearer token authorization.

HawkScan supports this scenario by adding `usernamePassword`, `tokenExtraction`, and `tokenAuthorization` configurations to `app.authentication`.

Configuring `usernamePassword` for this scenario is similar to the first scenario , but instead the `usernamePassword.type=JSON` which will cause the credential and `otherParams` to be POSTed as `application/json` instead of `application/x-www-form-urlencoded`. Successful authentication will return a `JSON` payload containing the bearer token that will need to be passed with every request to an authenticated route.

For more help configuring Token Authentidation, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/authenticated-scanning.html#usernamepassword-authentication--bearer-token-authorization)

#### Running the scanner with multiiple config files
To better support advanced configurations you can provide multiple configuration files as an overlay to the base scan configuration `stackhawk.yml`. Subsequent configuration files will be merged on top of the prior, effectively replacing any duplicate setting values form the previous scan configuration file.

```
docker run --name hawkscan --network host -e API_KEY=${API_KEY} --rm -v $(pwd):/hawk:rw -t stackhawk/hawkscan:latest stackhawk-graphql.yml stackhawk-cookie.yml
```
