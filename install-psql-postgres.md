This is a guide for installing `psql/postgres` on macOS.

## 1. Install Homebrew

First, we are going to install Homebrew, a package manager for macOS.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Source: https://brew.sh/

## 2. Install postgres

```
brew update
brew install postgresql
```

We can now check our installation by running a postgres server and checking its version.

```
pg_ctl -D /usr/local/var/postgres start
postgres -V
```

But it's annoying to type out that lengthly command every time. So, let's change that.

## 3. Change postgres PATH

For mojave and earlier:

```
code ~/.bash_profile
```

Add this to the end of the .bash_profile file.

```
# Set location of storage area for PostgreSQL
export PGDATA=/usr/local/var/postgres
```

## 4. Create default user and database for psql

```
createuser -Pw --interactive
```

In the bash_profile again:

```
# Override the default user in PSQL
export PGUSER=postgres
```
