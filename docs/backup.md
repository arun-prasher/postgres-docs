# PostgreSQL Backup

## Backup one database

```bash
pg_dump -h 127.0.0.1 -U postgres -d mydb > mydb.sql
```

## Restore one database

```bash
psql -h 127.0.0.1 -U postgres -d mydb < mydb.sql
```

## Backup all databases

```bash
pg_dumpall -U postgres > all_databases.sql
```

## Tips

- Test restores regularly
- Keep backups off-server
- Protect backup files carefully
