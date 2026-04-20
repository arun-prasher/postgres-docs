# Getting Started with PostgreSQL

## What is PostgreSQL?

PostgreSQL is an open-source relational database management system (RDBMS). It is used to store, manage, and query structured data.

It supports:

- SQL
- transactions
- indexes
- views
- functions
- roles and permissions
- JSON data
- extensions

## Basic terms

### Database
A database is a container that holds schemas, tables, views, functions, and other objects.

### Table
A table stores data in rows and columns.

### Row
A row is one record in a table.

### Column
A column defines one field of data.

### Role
A role is used for login, ownership, and permissions.

### Schema
A schema is a namespace inside a database that groups objects.

## First connection example

```bash
psql -h 127.0.0.1 -U postgres -d postgres
```

### Explanation

- `-h` = host
- `-U` = username
- `-d` = database name

If `-d` is not provided, `psql` tries to connect to a database with the same name as the user.

## First useful commands

Inside `psql`:

```sql
\l
\du
\dn
\dt
```

- `\l` = list databases
- `\du` = list roles
- `\dn` = list schemas
- `\dt` = list tables

## Example: create a database

```sql
CREATE DATABASE myapp;
```

## Example: create a role

```sql
CREATE ROLE myuser WITH LOGIN PASSWORD 'mypassword';
```

## Example: grant database access

```sql
GRANT CONNECT ON DATABASE myapp TO myuser;
```
