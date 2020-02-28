## Express/Postgres Reference

### Installation

Install knex (lets you use .sql in javascript):

```
npm i knex
```

Install Postgrator (used for migrations):

```
npm install postgrator-cli --save-dev
```

Knex Driver for Postgrator:

```
npm i pg
```

Sanitizing tool:

```
npm i xss
```

Move example.env to .env with:

```
mv example.env .env
```

### Commands

Start Postgres with:

```
postgres
```

Reset Postgres (postmaster.pid errors) with:

```
pg_ctl -D /usr/local/var/postgres stop -s -m fast
```

After Postgres is started, Create Database with:

```
createdb -U <user> <database>
createdb -U dunder_mifflin blogful-test
```

Examples of Migration Commands:

```
npm run migrate -- 0
npm run migrate
npm run migrate:test
```

Seeding database command:

```
psql -U <user> -d <database> -f <seed-file>

psql -U dunder_mifflin -d blogful -f ./seeds/seed.blogful_articles.sql
```

---

Logging into a Postgres database:

```
psql -U <user> -d <database>
psql -U dunder_mifflin -d products
```

---

Create a user:

```
# make sure you're in normal bash prompt, not in the psql prompt
createuser -Pw --interactive
```

Login with user:

```
psql -U <username> postgres
psql -U test postgres
```

Create Database (psql):

```
CREATE DATABASE <name>;
CREATE DATABASE routing;
```

Check if Database was created (psql):

```
\l
```
