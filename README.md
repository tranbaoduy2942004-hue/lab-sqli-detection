# SQL Injection & SOC Detection

A lightweight standalone Labtainer cybersecurity lab.

## Architecture

- Attacker: SQL Injection simulation
- WebApp: vulnerable Python + SQLite application
- SOC: authentication event collection and correlation

The vulnerability is intentional and restricted to the isolated training environment.

## Installation

On a Labtainer VM:

```bash
imodule https://raw.githubusercontent.com/tranbaoduy2942004-hue/lab-sqli-detection/main/imodule.tar
labtainer lab-sqli-detection
```

## Run Simulation

After starting the lab, run these commands on the Labtainer host:

Start SOC:

```bash
docker exec -d -u ubuntu -e HOME=/home/ubuntu lab-sqli-detection.soc.student lab09-soc
```

Start WebApp:

```bash
docker exec -d -u ubuntu -e HOME=/home/ubuntu lab-sqli-detection.webapp.student lab09-web
```

Run SQL Injection:

```bash
docker exec -u ubuntu -e HOME=/home/ubuntu lab-sqli-detection.attacker.student lab09-attack
```

Run SOC Detection:

```bash
docker exec -u ubuntu -e HOME=/home/ubuntu lab-sqli-detection.soc.student lab09-soc --detect
```

Check Grader:

```bash
checkwork
```

## Assessment

5/5 goals passed in the development environment.

## Docker Hub

https://hub.docker.com/u/tranbaoduy

## Status

- Development test: PASS
- Docker images: Published
- Clean VM installation: Pending verification
