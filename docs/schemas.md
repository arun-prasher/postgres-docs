# PostgreSQL Schemas

A schema is a namespace inside a database. It helps organize database objects like tables, views, functions, and sequences.

## Why schemas matter

- Organize objects
- Separate modules
- Support multi-tenant design
- Help with access control

## Create a schema

```sql
CREATE SCHEMA app;
```

## Grant access to a schema

```sql
GRANT USAGE ON SCHEMA app TO tenant_user;
```

## Allow object creation in a schema

```sql
GRANT CREATE ON SCHEMA app TO tenant_user;
```

## List schemas

```sql
\dn
```

## Show schema privileges

```sql
\dn+
```
