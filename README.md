# prometheus-enviro-consoles

Table of Contents

* [Features](#features)
* [Setup](#setup)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Resources](#resources)

## Features

Prometheus consoles displaying metrics collected by [prometheus-enviro-exporter](https://github.com/terradolor/prometheus-enviro-exporter).

* table overview listing all exporter targets
* detailed view with graphs for one exporter (i.e. one Enviro sensor)
* values for all sensors are displayed

## Setup

### Prerequisites

1. Prometheus server up and running, somewhere
    * For Debian-based systems: `apt instal prometheus`
    * Consoles are implemented and tested against Prometheus version from Debian Bullseye
2. Enabled default consoles from Prometheus project
    * On Debian-based systems read `/etc/prometheus/consoles/README.consoles`, which means:

      ```sh
      cp /usr/share/doc/prometheus/examples/consoles/* /etc/prometheus/consoles/
      cp /usr/share/doc/prometheus/examples/console_libraries/* /etc/prometheus/console_libraries/
      cp /etc/prometheus/consoles/index.html.example /etc/prometheus/consoles/index.html
      service prometheus restart
      ```

    * Afterwards you should see `Consoles` in Prometheus web UI menu bar
3. At least one configured and running instance of [prometheus-enviro-exporter](https://github.com/terradolor/prometheus-enviro-exporter).
  Otherwise there will be nothing to display ;)

### Installation

As root on Prometheus server

```sh
git clone https://github.com/terradolor/prometheus-enviro-consoles.git
cp prometheus-enviro-consoles/consoles/* /etc/prometheus/consoles/
```

New consoles are available on: `http://<prometheus_server>:9090/consoles/enviro.html`

## Resources

* [Documentation of Prometheus console templates](https://prometheus.io/docs/visualization/consoles/)
