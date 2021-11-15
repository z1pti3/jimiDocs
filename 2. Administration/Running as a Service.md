---
sort: 4
---

# Running as a Service

This page contains sample linux service files that can be used.

Files can be saved into

```
/etc/systemd/service/
```

## jimi_core

```
[Unit]
Description=jimi_core

[Service]
Type=simple
User=jimi
Group=jimi
WorkingDirectory=/opt/jimi/
ExecStart=/usr/bin/python3 /opt/jimi/jimi_core.py --config /opt/jimi/data/settings.json

[Install]
WantedBy=multi-user.target
```

## jimi_web

```
[Unit]
Description=jimi_web

[Service]
Type=simple
User=jimi
Group=jimi
WorkingDirectory=/opt/jimi/
ExecStart=/usr/bin/python3 /opt/jimi/jimi_web.py --config /opt/jimi/data/settings.json

[Install]
WantedBy=multi-user.target
```

