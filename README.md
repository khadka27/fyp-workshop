# The Database Design and Implementation

## Business Rules

- A user has a username, and a password, and many tweets
- A tweet has a content (250 characters, text only) and
  a timestamp for when it was created
- A followed (user) can have many followers
- A follower (user) can follow many followed (users)
- A user can have many tweets
- A tweet can belong to only one user

## ERD

The following ERD allows us to support all the features we
want.

![ERD](erd.svg)

## SQL Schema Code

The code for postgresql is available at `init.sql`
in the current folder.

```bash
# Create the database (connects to PostgreSQL as the default 'postgres' user)
psql -U postgres -c "CREATE DATABASE fyp;"

# Create the schema using the 'init.sql' file
psql -U postgres -d fyp -f init.sql

# Or, create the schema and seed the database using 'init.sql' and 'seed.sql'
psql -U postgres -d fyp -f init.sql -f seed.sql
```
