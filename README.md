<img width="800" alt="kaakaww-github-banner" src="https://user-images.githubusercontent.com/59268514/126686633-b8078990-16e2-4207-a97b-8d679b496274.png">

# Scan Configuration

HawkScan uses a YAML configuration file to supply operational settings to the scanner. To get started, copy the following into a file named stackhawk.yml in the root of your web app project directory. Replace URL_OF_YOUR_APP with the url of your locally running web app (example: http://localhost:3000) and the applicationId and env with the values from the StackHawk Platform.

#### By Application Type
* [Default Configuration]()
* [REST API]()
* [GraphQL API]()
* [SOAP API]()

#### Authenticated Scanning



### Running the scanner

#### Bash
```bash
docker run --name hawkscan --network host -e API_KEY=${API_KEY} --rm -v $(pwd):/hawk:rw -it stackhawk/hawkscan:latest
```

#### PowerShell
```PowerShell
docker run --rm -v ${PWD}:/hawk -e API_KEY=hawk.xxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxx -it stackhawk/hawkscan:latest
`
