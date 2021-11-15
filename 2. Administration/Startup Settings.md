---
sort: 3
---

# Startup Settings

Although most settings are defined within your jimi instance, there are some settings that can only be defined before starting jimi. Startup settings are normally limited to service binding and database config.

## Command Line Arguments

Command line arguments are possible for both jimi_core and jimi_web and can be located by appending --help.

```
python3 jimi_core.py --help
usage: jimi_core.py [-h] [--config CONFIG] [--id ID] [--ip IP] [--secure SECURE] [--max_workers MAX_WORKERS]
                    [--core_bind_address CORE_BIND_ADDRESS] [--core_bind_port CORE_BIND_PORT]
                    [--worker_bind_address WORKER_BIND_ADDRESS] [--worker_bind_port_start WORKER_BIND_PORT_START]
                    [--web_bind_address WEB_BIND_ADDRESS] [--web_bind_port WEB_BIND_PORT] [--db_host DB_HOST]
                    [--db_username DB_USERNAME] [--db_password DB_PASSWORD] [--db DB]

optional arguments:
  -h, --help            show this help message and exit
  --config CONFIG       Path to settings.json
  --id ID               System ID value
  --ip IP               Primary network address ( ip ) uses to address this system
  --secure SECURE       Enable TLS for internal jimi API
  --max_workers MAX_WORKERS
                        Maxium number of workers
  --core_bind_address CORE_BIND_ADDRESS
                        Bind address for jimi_core
  --core_bind_port CORE_BIND_PORT
                        Bind port for jimi_core
  --worker_bind_address WORKER_BIND_ADDRESS
                        Bind address for jimi_core workers
  --worker_bind_port_start WORKER_BIND_PORT_START
                        Bind port start for jimi_core workers
  --web_bind_address WEB_BIND_ADDRESS
                        Bind address for jimi_web
  --web_bind_port WEB_BIND_PORT
                        Bind port for jimi_core
  --db_host DB_HOST     Database connection details i.e. 127.0.0.1:27017
  --db_username DB_USERNAME
                        Database username
  --db_password DB_PASSWORD
                        Database password
  --db DB               Database name to use
```

### MongoDB Connection Strings

As well as the standard host, username, password settings it is possible to use a connection string to connect.

Currently connection strings MUST be deined within settings.json.

```
"mongodb": {
    "connectString" : "mongodb+srv://jimi:<PASSWORD>@<HOSTADDRESS>/jimi?authSource=admin&replicaSet=jimi-db&tls=true&tlsCAFile=data/mongo.pem",
    "db" : "jimi"
}
```

Note db is still required when using a connection string.