---
sort: 1
---

# Manual

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
    "system" : {
        "systemID" : 0,
        "accessAddress" : "<JIMI_CORE_ADDRESS>",
        "accessPort" : 5000,
        "secure" : false
    },
    "debug" : {
        "level" : -1,
        "buffer" : 1000
    },
    "static" : {
    },
    "mongodb": {
        "hosts" : ["<DB_HOST>:27017"],
        "db" : "dev",
        "username" : null,
        "password" : null
    },
    "api": {
        "core" : {
            "bind" : "<JIMI_CORE_ADDRESS>",
            "port" : 5000,
            "base" : "api/1.0",
            "apiKey" : null
        },
        "worker" : {
            "bind" : "127.0.0.1",
            "startPort" : 5001,
            "base" : "api/1.0",
            "apiKey" : null
        },
        "web" : {
            "bind" : "0.0.0.0",
            "port" : 5015,
            "base" : "api/1.0",
            "apiKey" : null
        },
        "proxy" : {
            "http" : null,
            "https" : null
        }
    },
    "workers" : { 
        "concurrent" : 15,
        "loopT" : 0.01,
        "loopT1" : 0.25,
        "loopL" : 200
    },
    "cpuSaver" : { 
        "enabled" : true,
        "loopT" : 0.01,
        "loopL" : 100
    },
    "scheduler" : {
        "loopP" : 5
    },
    "cluster" : {
        "loopP" : 10,
        "recoveryTime" : 60,
        "deadTimer" : 30
    },
    "audit" : {
        "db" : {
            "enabled" : true
        },
        "file" : {
            "enabled" : true,
            "logdir" : "log"
        }
    },
    "auth" : {
        "enabled" : true,
        "sessionTimeout" : 1800,
        "apiSessionTimeout" : 300,
        "cacheSessionTimeout" : 60,
        "singleUserSessions" : true,
        "rsa" : {
            "cert" : "data/sessionPub.pem",
            "key" : "data/sessionPriv.pem"
        },
        "policy" : {
            "minLength" : 8,
            "minNumbers" : 1,
            "minLower" : 1,
            "minUpper" : 1,
            "minSpecial" : 0
        }
    },
    "cache" : {
        "garbageCollector" : true
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

**NOTE: 
For production workloads we recommend that jimi_web is run with a WSGI such as gunicorn, fronted by Apache. jimi_core should also be run by a dedicated user and not root.**

If all has gone well then jimi should now be up and running and browsing to http://127.0.0.1:5002 should display the login page. 
