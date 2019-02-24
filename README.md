# mozob
Docker files to pull together Mozilla's TLS &amp; HTTP Observatories

* Containers:
 * api_httpobs - HTTP Observatory API (https://github.com/mozilla/http-observatory)
 * scanner_httpobs - HTTP Scanner
 * api_tlsobs - TLS Observatory API (https://github.com/mozilla/tls-observatory)
 * scanner_tlsobs - TLS Scanner
 * redis - Redis ;-)
 * db_httpobs - Postgres for HTTP Observatory
 * db_tlsobs - Postgres for TLS Observatory
 * website - Web GUI (https://github.com/mozilla/http-observatory-website)

## Install

```
git clone https://github.com/linickx/mozob.git mozob
cd mozob
docker-compose up
```

## Basic API Usage

1. Start a HTTP SCAN: `curl http://localhost:57001/api/v1/analyze?host=www.google.com -X POST -d "rescan=true"`
2. Start a TLS SCAN: `curl -X POST http://localhost:8083/api/v1/scan?target=www.google.com -d "rescan=true"`
3. Retrieve HTTP SCAN `curl http://localhost:57001/api/v1/analyze?host=www.google.com`
4. Retrieve TLS SCAN: `curl http://localhost:8083/api/v1/results?id=1`

TLS API: https://github.com/mozilla/tls-observatory#api-endpoints
HTTP API: https://github.com/mozilla/http-observatory/blob/master/httpobs/docs/api.md


## TODO

* Replace credentials from `schema.sql.docker.sql` (Postgres x2) with ENV VARS.