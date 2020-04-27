[![Github Release Version](https://img.shields.io/badge/release-V1.0-blue.svg)](https://github.com/flipkart-incubator/Astra)
[![Github Release Version](https://img.shields.io/badge/python-2.7-blue.svg)](https://github.com/flipkart-incubator/Astra)

[![BH 2018 USA](https://img.shields.io/badge/Black%20Hat%20Arsenal-USA%202018-blue.svg)](https://www.blackhat.com/us-18/arsenal/schedule/index.html#astra-automated-security-testing-for-rest-apis-11976)

[![BH 2018 Europe](https://img.shields.io/badge/Black%20Hat%20Arsenal-Europe%202018-blue.svg)](https://www.blackhat.com/eu-18/arsenal/schedule/index.html#astra-automated-security-testing-for-rest-apis-13353)

## Astra
![alt text](https://raw.githubusercontent.com/flipkart-incubator/Astra/dev/Dashboard/static/astra.png)

REST API penetration testing is complex due to continuous changes in existing APIs and newly added APIs. Astra can be used by security engineers or developers as an integral part of their process, so they can detect and patch vulnerabilities early during development cycle. Astra can automatically detect and test login & logout (Authentication API), so it's easy for anyone to integrate this into CICD pipeline. Astra can take API collection as an input so this can also be used for testing apis in standalone mode.

- SQL injection
- Cross site scripting
- Information Leakage
- Broken Authentication and session management
- CSRF (including Blind CSRF)
- Rate limit
- CORS misconfiguration (including CORS bypass techniques)
- JWT attack
- CRLF detection
- Blind XXE injection 

## Roadmap
[https://www.astra-security.info/roadmap/](https://www.astra-security.info/roadmap/)

## Documentation
[https://www.astra-security.info](https://www.astra-security.info)

## Requirements
- Linux or MacOS
- python 2.7
- mongoDB
- docker

## Installation

```
cd /usr/share/ && git clone https://github.com/flipkart-incubator/Astra && cd Astra && wget https://bootstrap.pypa.io/get-pip.py && sudo python get-pip.py && sudo pip install -r requirements.txt && pip install requests logger pymongo ConfigParser pyjwt flask sqlmap
```

## Docker Installation

1. To install go [here](https://docs.docker.com/engine/install/) and follow the instructions proivided there.

2. Start Docker
```
docker --version && sudo service docker start && sudo systemctl enable docker && sudo service docker status
```

### MongoDB 

1. To install go [here](https://docs.mongodb.com/manual/administration/install-on-linux/) and follow the instructions proivided there.

2. Start MongoDB Database Server
```
mongo --version && sudo service mongod start && sudo systemctl enable mongod && sudo service mongod status
```

### Run Astra-Mongo Container:

```
cd /usr/share/Astra && docker pull mongo
```

```
cd /usr/share/Astra && docker run --name astra-mongo -d mongo
```

### Installing GUI Docker: 

```
cd /usr/share/Astra && docker build -t astra .
```

```
cd /usr/share/Astra && docker run --rm -it --link astra-mongo:mongo -p 8094:8094 astra
```

### Installing CLI Docker :

```
cd /usr/share/Astra && docker build -t astra-cli .
```

```
cd /usr/share/Astra && docker run --rm -it --link astra-mongo:mongo astra-cli
```

#
## Web interface Usage:
Execute
```
cd /usr/share/Astra/API && python api.py
```
Now access the web interface at http://127.0.0.1:8094

#
#
## CLI Usage:

```
cd /usr/share/Astra && python astra.py --help

                      _
        /\       | |
       /  \   ___| |_ _ __ __ _
      / /\ \ / __| __| '__/ _` |
     / ____ \__ \ |_| | | (_| |
    /_/    \_\___/\__|_|  \__,_|



usage: astra.py [-h] [-c {Postman,Swagger}] [-n COLLECTION_NAME] [-u URL]
                [-headers HEADERS] [-method {GET,POST}] [-b BODY]
                [-l LOGINURL] [-H LOGINHEADERS] [-d LOGINDATA]

REST API Security testing Framework

optional arguments:
  -h, --help            show this help message and exit
  -c {Postman,Swagger}, --collection_type {Postman,Swagger}
                        Type of API collection
  -n COLLECTION_NAME, --collection_name COLLECTION_NAME
                        Type of API collection
  -u URL, --url URL     URL of target API
  -headers HEADERS, --headers HEADERS
                        Custom headers.Example: {"token" : "123"}
  -method {GET,POST}, --method {GET,POST}
                        HTTP request method
  -b BODY, --body BODY  Request body of API
  -l LOGINURL, --loginurl LOGINURL
                        URL of login API
  -H LOGINHEADERS, --loginheaders LOGINHEADERS
                        Headers should be in a dictionary format. Example:
                        {"accesstoken" : "axzvbqdadf"}
  -d LOGINDATA, --logindata LOGINDATA
                        login data of API

```

## Screenshots 
### New scan
![alt text](https://raw.githubusercontent.com/flipkart-incubator/Astra/dev/Dashboard/static/new%20scan.png)

### Scan Reports
![alt text](https://raw.githubusercontent.com/flipkart-incubator/Astra/dev/Dashboard/static/Reports.png)

![alt text](https://raw.githubusercontent.com/flipkart-incubator/Astra/dev/Dashboard/static/scan-report.png)
### Detailed Report
![alt text](https://raw.githubusercontent.com/flipkart-incubator/Astra/dev/Dashboard/static/Detailed-report.png)


## Lead Developer
- Sagar Popat (@popat_sagar) 

## Credits
- Ankur Bhargava
- Harsh Grover
- Flipkart security team
- Pardeep Battu

