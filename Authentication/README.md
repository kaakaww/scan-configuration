<img width="100%" alt="kaakaww-github-banner" src="https://user-images.githubusercontent.com/59268514/126686633-b8078990-16e2-4207-a97b-8d679b496274.png">

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

# Authenticated Scanning with StackHawk

Most web applications will have specific pages that are only accessible to authenticated users. To effectively scan for vulnerabilities it is important to test all paths, including the authenticated routes.

HawkScan can support authentication via `usernamePassword` or an `external supplied authorization token`. In addition, you can configure how HawkScan maintains authentication throughout the scan via a `cookieAuthorization` or `tokenAuthorization` configuration.

A testPath configuration may also be provided to verify HawkScan authenticated its session correctly before scanning the application. The testPath configuration also provides requestMethod and requestBody options to support alternate HTTP request verbs, such as POST or PUT. The default action is GET.


For more help configuring Authentication, see our [Documentation](https://docs.stackhawk.com/hawkscan/configuration/authenticated-scanning.html)

### Getting Started

| Authentication Type                                                               | Use Case                                                                |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [Username/Password Authentication + Cookie Authorization](Cookie_Auth)            | POSTing a credentials which return a cookie used to track user sessions |
| [Username/Password Authentication + Bearer Token Authorization](Token_Auth)       | APIs accepting credentials via a POST request of JSON data              |
| [External Token Authentication + Custom Token Authorization](External_Token_Auth) | Third-party authentication services                                     |
---
