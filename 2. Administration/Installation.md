---
sort: 1
---

# Installation

## Prerequisites
* mongodb 4.2+ - [How to install](https://docs.mongodb.com/manual/administration/install-on-linux/)
* python3 - [How to install](https://docs.python-guide.org/starting/install3/linux/)
* python3-pip

## jimi
1. Clone repository
```
git clone https://github.com/z1pti3/jimi.git
```

2. Change directory into jimi
```
cd jimi
```

3. Install dependencies from requirements.txt
```
pip install -r requirements.txt
```

4. Make a log and plugins directory 
```
mkdir log
mkdir plugins
```

5. Make a data directory
```
mkdir data
```

6. Change directory into data
```
cd data
mkdir temp
```

7. Generate an rsa public private key pair
```
openssl genrsa -des3 -out private.pem 2048
openssl rsa -in private.pem -outform PEM -pubout -out sessionPub.pem
openssl rsa -in private.pem -out sessionPriv.pem -outform PEM
rm private.pem
```

8. Create a settings.json
```
nano settings.json
```

```
{
    {
    "system" : {
        "systemID" : 0,
        "accessAddress" : "127.0.0.1",
        "accessPort" : 5000,
        "secure" : false,
        "max_workers" : 1
    },
    "mongodb": {
        "hosts" : ["127.0.0.1:27017"],
        "db" : "jimi",
        "username" : null,
        "password" : null
    },
    "api": {
        "base" : "api/1.0",
        "core" : {
            "bind" : "127.0.0.1",
            "port" : 5000
        },
        "worker" : {
            "bind" : "127.0.0.1",
            "startPort" : 5001
        },
        "web" : {
            "bind" : "0.0.0.0",
            "port" : 5015
        }
    }
}
```

9. Navigate to jimi/ directory
```
cd ..
```

10. Run jimi_core.py
```
python3 jimi_core.py
```

11. Pay careful attention to the install output as the root password is generated and output only on first run

12. Run jimi_web.py
```
python3 jimi_web.py
```

If all has gone well then jimi should now be up and running and browsing to http://127.0.0.1:5015 should display the login page. 
