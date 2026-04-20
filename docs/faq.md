# PostgreSQL FAQ

## Why does psql say database does not exist?

If you run:

```bash
psql -h 127.0.0.1 -U tenant_user -p 5432
```

and do not provide `-d`, `psql` tries to connect to a database with the same name as the username.

### Fix

```bash
psql -h 127.0.0.1 -U tenant_user -p 5432 -d postgres
```

## What is the difference between role and user in PostgreSQL?

In PostgreSQL, both are handled using roles. If a role has `LOGIN`, it can act like a user.

## What is the difference between `PUBLIC` and `public`?

- `PUBLIC` means all roles
- `public` is the default schema name

## Why am I getting permission denied even after granting table access?

A user may also need:
- `CONNECT` on database
- `USAGE` on schema
- sequence privileges for inserts
