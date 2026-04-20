# PostgreSQL Permissions

PostgreSQL permissions work in layers. Understanding the layers makes debugging much easier.

## Permission layers

1. Authentication
2. Role attributes
3. Database privileges
4. Schema privileges
5. Object privileges
6. Ownership
7. Role membership
8. Default privileges

## Role attributes

Common role attributes:

- `LOGIN`
- `SUPERUSER`
- `CREATEDB`
- `CREATEROLE`

Check role attributes:

```sql
SELECT rolname, rolsuper, rolcreatedb, rolcreaterole, rolcanlogin
FROM pg_roles
WHERE rolname = 'tenant_user';
```

## Database privileges

Important database privileges:

- `CONNECT`
- `CREATE`
- `TEMPORARY`

Example:

```sql
GRANT CONNECT ON DATABASE mydb TO tenant_user;
```

## Schema privileges

Important schema privileges:

- `USAGE`
- `CREATE`

Example:

```sql
GRANT USAGE ON SCHEMA public TO tenant_user;
```

## Table privileges

Common table privileges:

- `SELECT`
- `INSERT`
- `UPDATE`
- `DELETE`

Example:

```sql
GRANT SELECT, INSERT, UPDATE, DELETE
ON ALL TABLES IN SCHEMA public
TO tenant_user;
```

## Sequence privileges

Sequence permissions are separate from table permissions.

```sql
GRANT USAGE, SELECT, UPDATE
ON ALL SEQUENCES IN SCHEMA public
TO tenant_user;
```

## Useful inspection commands

```sql
\du
\l
\dn+
\dp
```

## Default privileges

Grants on existing tables do not automatically apply to future tables.

```sql
ALTER DEFAULT PRIVILEGES IN SCHEMA public
GRANT SELECT, INSERT, UPDATE, DELETE ON TABLES TO tenant_user;
```
