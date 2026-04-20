# PostgreSQL User Guide

This page contains common PostgreSQL tasks and commands for daily use.

## Connect to PostgreSQL

```bash
psql -h 127.0.0.1 -U postgres -d postgres
```

## List databases

```sql
\l
```

## List roles

```sql
\du
```

## List schemas

```sql
\dn
```

## List tables

```sql
\dt
```

## Create table

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(255) UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Insert data

```sql
INSERT INTO users (name, email)
VALUES ('Arun', 'arun@example.com');
```

## Read data

```sql
SELECT * FROM users;
```

## Update data

```sql
UPDATE users
SET name = 'Arun Prasher'
WHERE id = 1;
```

## Delete data

```sql
DELETE FROM users
WHERE id = 1;
```

## Grant permissions

```sql
GRANT CONNECT ON DATABASE mydb TO tenant_user;
GRANT USAGE ON SCHEMA public TO tenant_user;
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO tenant_user;
GRANT USAGE, SELECT, UPDATE ON ALL SEQUENCES IN SCHEMA public TO tenant_user;
```

## Helpful tips

- Always specify the database using `-d`
- Use roles instead of sharing one admin account
- Grant only required permissions
- Separate app users from admin users
