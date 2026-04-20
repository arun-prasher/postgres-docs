# PostgreSQL Installation

This page covers the basic installation process for PostgreSQL.

## Install on Ubuntu

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

## Check service status

```bash
sudo systemctl status postgresql
```

## Start PostgreSQL

```bash
sudo systemctl start postgresql
```

## Enable PostgreSQL on boot

```bash
sudo systemctl enable postgresql
```

## Switch to postgres user

```bash
sudo -u postgres psql
```

## Check PostgreSQL version

```bash
psql --version
```

## Default port

PostgreSQL usually runs on port `5432`.

## Connect to a database

```bash
psql -h 127.0.0.1 -U myuser -d mydb
```

## Common installation checks

```bash
ss -ltnp | grep 5432
```

## Common issues after installation

- Connection refused
- Password authentication failed
- Database does not exist
