# Database Mistake Log

## Common Mistakes I've Made

- Missing primary keys
- Using SELECT \*
- No indexing → slow queries
- Overuse of joins
- Wrong partition key
- Violating normalization rules
- Misusing NoSQL for relational data

## Fix Strategy

- Always inspect EXPLAIN
- Create indexes early
- Learn normalization/denormalization trade-offs
- Understand access patterns
