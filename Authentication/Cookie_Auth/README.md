# Cookie Authentication

A common way to authenticate to a web application is by POSTing a username and password which can be verified by your server. Upon verification the server returns a new cookie to the requesting client.

This is the standard behavior for cookie-based authorization schemes. The cookie is used to track your session on the server with the expectation that subsequent requests send the cookie back via the Set-Cookie response header. This allows the server to track requests and maintain the session.

The POST request for sending the username and password expects a payload type of application/x-www-form-urlencoded. The cookie verifying the users session will be named sessionid.

When a request with an invalid, or non-present cookie is sent the server will respond by redirecting the user to the /login page.


For more help configuring Cookie Authentication, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/authenticated-scanning.html#usernamepassword-authentication--cookie-authorization)


#### Running the scanner with multiiple config files
To better support advanced configurations you can provide multiple configuration files as an overlay to the base scan configuration `stackhawk.yml`. Subsequent configuration files will be merged on top of the prior, effectively replacing any duplicate setting values form the previous scan configuration file.


```
docker run --name hawkscan --network host -e API_KEY=${API_KEY} --rm -v $(pwd):/hawk:rw -t stackhawk/hawkscan:latest stackhawk-graphql.yml stackhawk-cookie.yml
```
