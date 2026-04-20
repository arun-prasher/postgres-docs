# PostgreSQL Troubleshooting

## Common connection issue

### Error
`FATAL: database "tenant_user" does not exist`

### Reason
`psql` defaults the database name to the same value as the username if `-d` is not provided.

### Fix

```bash
psql -h 127.0.0.1 -U tenant_user -d postgres
```

## Permission denied on table

Check:

- database `CONNECT`
- schema `USAGE`
- table privileges
- sequence privileges

## Permission denied for sequence

Fix:

```sql
GRANT USAGE, SELECT, UPDATE ON ALL SEQUENCES IN SCHEMA public TO tenant_user;
```

## Service is not running

```bash
sudo systemctl status postgresql
sudo systemctl start postgresql
```
