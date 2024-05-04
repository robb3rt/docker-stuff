## Overview

Contains a docker-compose file which starts a Prometheus server that can be integrated with Stream.

To start Prometheus, just run `docker compose up`.

## Scraper

To set up a Prometheus Scraper, set the Targets to `http://localhost:9090/metrics`. The rest of the settings can be left
as defaults.

## Remote Write Source

To set up a Prometheus Remote Write source, set the port to `9201`. The rest of the settings can be left as defaults.

## Remote Write Destination

To set up a Prometheus Remote Write destination, set the `Remote Write URL` to `http://localhost:9090/api/v1/write`. 
The rest of the settings can be left as defaults.

## Not Configured For Testing

The following aspects are not configured for testing -

 - Authentication
 - TLS

