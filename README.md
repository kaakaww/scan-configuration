<img width="800" alt="kaakaww-github-banner" src="https://user-images.githubusercontent.com/59268514/126686633-b8078990-16e2-4207-a97b-8d679b496274.png">

# Scan Configuration

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

To find more information about HawkScan check out our [Documentation](https://docs.stackhawk.com)


## Overview
StackHawk is a dynamic application security testing (DAST) tool built for developers. The StackHawk scanner (HawkScan) utilizes a YAML configuration file to supply operational settings to the scanner. To get started clone this repo and place the `stackhawk.yml` file into the root of your project directory.


### Configuration Files
* [Basic Configuration](Basic)
* [REST API]()
* [GraphQL API]()
* [SOAP API]()

### Authenticated Scanning
* [Cookie Authentication]()
* [Token Authentication]()
* [External Token Authentication]()


### Running the scanner

#### Bash
```bash
docker run --name hawkscan --network host -e API_KEY=${API_KEY} --rm -v $(pwd):/hawk:rw -it stackhawk/hawkscan:latest
```

#### PowerShell
```PowerShell
docker run --rm -v ${PWD}:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
`
