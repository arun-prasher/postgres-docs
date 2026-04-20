# PostgreSQL Performance

Performance tuning starts with good queries and proper indexes.

## Key areas

- query design
- indexes
- vacuum and analyze
- configuration tuning
- monitoring slow queries

## Explain a query

```sql
EXPLAIN SELECT * FROM users WHERE email = 'arun@example.com';
```

## Analyze actual execution

```sql
EXPLAIN ANALYZE SELECT * FROM users WHERE email = 'arun@example.com';
```

## Create an index

```sql
CREATE INDEX idx_users_email ON users(email);
```

## Keep learning

Add future notes here on:
- index types
- query plans
- autovacuum
- memory settings
