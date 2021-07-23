<img width="800" alt="kaakaww-github-banner" src="https://user-images.githubusercontent.com/59268514/126686633-b8078990-16e2-4207-a97b-8d679b496274.png">

# Scan Configuration

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

To learn more about HawkScan and configuration options, check out our [Documentation](https://docs.stackhawk.com)


## Overview
[StackHawk](https://www.stackhawk.com) is a dynamic application security testing (DAST) tool built for developers. The StackHawk scanner (HawkScan) utilizes a [YAML](https://yaml.org) configuration file to supply operational settings to the scanner. To get started clone this repo and place the appropriate `stackhawk.yml` file into the root of your project directory.


### Configuration Files
* [Basic Configuration](Basic)
* [REST API](REST)
* [GraphQL API](GraphQL)
* [SOAP API](SOAP)

### Authenticated Scanning
* [Cookie Authentication](Cookie_Auth)
* [Token Authentication](Token_Auth)
* [External Token Authentication](External_Token_Auth)


### Running the scanner

#### Bash
```bash
docker run --rm -v $(pwd):/hawk:rw -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
```

#### Windows CLI
```bash
docker run --rm -v %cd%:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
```

#### PowerShell
```PowerShell
docker run --rm -v ${PWD}:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
```

#### Linux
```PowerShell
docker run --rm -v $(pwd):/hawk:rw -network host -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
```

For more help configuring Hawkscan, see our [Documentation](https://docs.stackhawk.com/hawkscan).
