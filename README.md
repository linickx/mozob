# mozob
Docker files to pull together Mozilla's TLS &amp; HTTP Observatories

## Install

```
git clone https://github.com/linickx/mozob.git mozob
cd mozob
docker-compose up
```

## Usage

1. Start a HTTP SCAN: `curl http://localhost:57001/api/v1/analyze?host=www.google.com -X POST -d "rescan=true"`
2. Start a TLS SCAN: `curl -X POST http://localhost:8083//api/v1/scan?target=www.google.com -d "rescan=true"`
3. Retrieve HTTP SCAN `http://localhost:57001/api/v1/results?id=1`
4. Retrieve TLS SCAN: `http://localhost:8083/api/v1/results?id=1`


## TODO

* Replace credentials from `schema.sql.docker.sql` (Postgres x2) with ENV VARS.