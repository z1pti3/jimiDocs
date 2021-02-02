---
sort: 2
---

# Manual

## Prerequisites
* mongodb 4.2+
* python3

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
        "accessAddress" : "<jim_core HOST>",
        "accessPort" : <jim_core PORT>,
        "secure" : false
    },
    "debug" : {
        "level" : -1,
        "buffer" : 1000
    },
    "static" : {
    },
    "mongodb": {
        "hosts" : ["<HOST>:<PORT>"],
        "db" : "<DBNAME>",
        "username" : null,
        "password" : null
    },
    "api": {
        "core" : {
            "bind" : "127.0.0.1",
            "port" : 5000,
            "base" : "api/1.0",
            "apiKey" : null
        },
        "web" : {
            "bind" : "0.0.0.0",
            "port" : 5002,
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
    }
}
```

9. Run jimi_core.py
```
python3 jimi_core.py
```

10. Pay careful attention to the install output as the root password is generated and output only on first run

11. Run jimi_web.py
```
python3 jimi_web.py
```

**NOTE: 
For production workloads we recommend that jimi_web is run with a WSGI such as gunicorn, fronted by Apache. jimi_core should also be run by a dedicated user and not root.**

If all has gone well then jimi should now be up and running and browsing to http://127.0.0.1:5002 should display the login page. 
