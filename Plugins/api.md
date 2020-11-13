---
sort: 4
---

# api

jimi api enables web requests to be made directly from a jimiFlow without the need of a dedicated plugin

## Download

[Download](https://github.com/z1pti3/jimiPlugin-api)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-api/archive/master.zip
unzip master.zip
mv jimiPlugin-api-master plugin/api
rm master.zip
```

## Actions

### api

Execute a defined api web request

**Properties:**

| Name | Description |
--- | ---
headers | A dictionary of headers items to include in the request - supports jimi string replacement syntax
url | the URL to call - supports jimi string replacement syntax
method | GET, POST, PUT, DELETE
ca | Path to a custom CA if required
postData | String containing the data to include with the request - supports jimi string replacement syntax
cookies | A dictionary of cookies - supports jimi string replacement syntax
timeout | Timeout value in seconds to wait for the request to complete
proxy | A dictionary in the following format to define a proxy if required { "http": None, "https": None }

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Done | True | <HTTP_STATUS_CODE> | data : { "headers", "text" }

The data returned is the response data provided by the webserver that served the request
