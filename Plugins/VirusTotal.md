---
sort: 1
---

# VirusTotal

Access to VirusTotal APIs from within a jimiFlow

## Download

[Download](https://github.com/z1pti3/jimiPlugin-virustotal)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-virustotal/archive/master.zip
unzip master.zip
mv jimiPlugin-virustotal-master plugin/virustotal
rm master.zip
```

## Actions

### virustotalIPDetails

Get threat intelligence information for a supplied IP address 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
apiToken | True | False | Your VirusTotal API key
ip | True | True | The IP for which information should be gathered.

**Returns:**

Returns a dictionary containing the ip analysis information

{ 
"last_modification_date"
"asn"
"as_owner" 
"country"
"network"
"reputation"
"whois"
"whois_date"
"harmless"
"malicious"
"suspicious"
"timeout"
"undetected"
"votes_harmless"
"votes_malicious"
"last_https_certificate_date"
"certificate_serial_number"
"certificate_thumbprint"
"certificate_thumbprint_sha256"
"certificate_not_after"
"certificate_not_before"
"certificate_subject"
}

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | None
Success | True | 0 | { "virustotal",  { API Result Dict } }

### virustotalDomainDetails

Get threat intelligence information for a supplied domain 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
apiToken | True | False | Your VirusTotal API key
domain | True | True | The domain for which information should be gathered.

**Returns:**

Returns a dictionary containing the domain analysis information

{ 
"last_modification_date"
"reputation"
"whois"
"whois_date"
"harmless"
"malicious"
"suspicious"
"timeout"
"undetected"
"votes_harmless"
"votes_malicious"
"last_dns_records_date"
"last_https_certificate_date"
"last_https_certificate_date"
"certificate_serial_number"
"certificate_thumbprint"
"certificate_thumbprint_sha256"
"certificate_not_after"
"certificate_not_before"
"certificate_subject"
}

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | None
Success | True | 0 | { "virustotal",  { API Result Dict } }

### virustotalFileDetails

Get threat intelligence information for a supplied sha256 file hash 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
apiToken | True | False | Your VirusTotal API key
sha256 | True | True | The sha256 file hash for which information should be gathered.

**Returns:**

Returns a dictionary containing the file analysis information

{ 
"sha256"
"last_modification_date"
"last_submission_date"
"last_analysis_date"
"reputation"
"whois"
"whois_date"
"harmless"
"malicious"
"suspicious"
"timeout"
"undetected"
"unsupported"
"failure"
"confirmed_timeout"
"meaningful_name"
"size"
"type_extension"
"unique_sources"
"type_tag"
"type_description"
"times_submitted"
"downloadable"
"votes_harmless"
"votes_malicious"
}

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | None
Success | True | 0 | { "virustotal",  { API Result Dict } }

### virustotalFileDBehaviour

Get threat extended file behaviour intelligence information for a supplied sha256 file hash 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
apiToken | True | False | Your VirusTotal API key
sha256 | True | True | The sha256 file hash for which behaviour information should be gathered.

**Returns:**

Returns a dictionary containing the file behaviour analysis information

Checkout VirusTotal developer API for details on what might be returned by the behaviour API  

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | None
Success | True | 0 | { "virustotal",  { API Result Dict } }

### virustotalFileDSubmission

Upload a file under 35MB to VirusTotal for analysis 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
apiToken | True | False | Your VirusTotal API key
filename | True | True | The local full filepath and filename that should be uploaded

**Returns:**

Returns a dictionary containing the file analysis information

{ 
"sha256"
"last_modification_date"
"last_submission_date"
"last_analysis_date"
"reputation"
"whois"
"whois_date"
"harmless"
"malicious"
"suspicious"
"timeout"
"undetected"
"unsupported"
"failure"
"confirmed_timeout"
"meaningful_name"
"size"
"type_extension"
"unique_sources"
"type_tag"
"type_description"
"times_submitted"
"downloadable"
"votes_harmless"
"votes_malicious"
}

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | None
Success | True | 0 | { "virustotal",  { API Result Dict } }
