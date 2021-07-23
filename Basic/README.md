# Scanning your application with StackHawk

For more information about StackHawk see [https://www.stackhawk.com](https://www.stackhawk.com)

#### TL;DR
1. Create an application on the [StackHawk Web platform](https://auth.stackhawk.com/login).
2. Clone this repo or copy the `stackhawk-basic.yml` or `stackhawk-default.yml` configuration file and place in the root of your project directory.

## Configuration

HawkScan uses a [YAML](https://yaml.org) configuration file to supply operational settings to the scanner. To get started:

* Place the appropriate `stackhawk.yml` file in the root of your project directory.
* Udpate your `applicationId` and `env` with the values from the StackHawk Platform.
* Update the `host` field with the url of your running web app (example: http://localhost:3000)


### Running the scanner

#### Bash
```bash
docker run --rm -v $(pwd):/hawk:rw -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-basic.yml
```

#### Windows CLI
```bash
docker run --rm -v %cd%:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-basic.yml
```

#### PowerShell
```PowerShell
docker run --rm -v ${PWD}:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-basic.yml
```

#### Linux
```PowerShell
docker run --rm -v $(pwd):/hawk:rw -network host -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -t stackhawk/hawkscan:latest stackhawk-basic.yml
```


For more help configuring Hawkscan, see our [Documentation](https://docs.stackhawk.com/hawkscan).
