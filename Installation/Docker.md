---
sort: 1
---

# Docker

## Prerequisites
* docker

## Option 1 -  Installer Script

`curl https://raw.githubusercontent.com/z1pti3/jimi-docker/master/jimiSetup.sh | bash`

## Option 2 -  Manual Deployment

Create a data directory

`mkdir data`

Create a plugin directory

`mkdir plugins`

To install recommended plugins run:
```
git clone https://github.com/z1pti3/jimiPlugin-subflow.git plugins/subflow
git clone https://github.com/z1pti3/jimiPlugin-humio.git plugins/humio
git clone https://github.com/z1pti3/jimiPlugin-script.git plugins/script
git clone https://github.com/z1pti3/jimiPlugin-event.git plugins/event
git clone https://github.com/z1pti3/jimiPlugin-occurrence.git plugins/occurrence
git clone https://github.com/z1pti3/jimiPlugin-testFire.git plugins/testFire
git clone https://github.com/z1pti3/jimiPlugin-email.git plugins/email
git clone https://github.com/z1pti3/jimiPlugin-remote.git plugins/remote
git clone https://github.com/z1pti3/jimiPlugin-api.git plugins/api
```

Create a db directory

`mkdir db`

Within the data directory create the settings.json; a working sample can be downloaded from:

https://raw.githubusercontent.com/z1pti3/jimi-docker/master/data/settings.json

Within the data directory create the public and private keys:
 ```
openssl genrsa -des3 -out private.pem 2048
openssl rsa -in private.pem -outform PEM -pubout -out sessionPub.pem
openssl rsa -in private.pem -out sessionPriv.pem -outform PEM
rm private.pem
```

Again within the data directory create the public and private keys required for the web server:

 ```
openssl req -newkey rsa:2048 -nodes -keyout web.key -x509 -days 365 -out web.cert
```

Finally, you will also need a folder called log that sits within the data directory

`mkdir log`

Download and run the latest images within a new network:

**NOTE** - Remember to update the -v with the paths to your folders created in the steps above.

```
docker network create jimi_network
docker run -d -v /home/ubuntu/jimi/db:/data/db --net jimi_network --name jimi_db mongo:latest
docker run -it -d -v /home/ubuntu/jimi/data:/home/jimi/jimi/data -v /home/ubuntu/jimi/plugins:/home/jimi/jimi/plugins --net jimi_network --name jimi_core z1pti3/jimi_core:amd64
docker run -it -d -p 5002:5002 -v /home/ubuntu/jimi/data:/home/jimi/jimi/data -v /home/ubuntu/jimi/plugins:/home/jimi/jimi/plugins --net jimi_network --name jimi_web z1pti3/jimi_web:amd64
```


View the logs of jimi_core to see the generated password:

`docker logs jimi_core`


Within your browser navigate to 

`https://<<jimi_web-IP>>:4443`
