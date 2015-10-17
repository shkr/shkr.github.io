---
layout: post
title:  Quick Start PostGres on MacOSx
---

If you have homebrew installed. We will use it to simplify our local
postgres installation for development.

> brew install postgres

After installation create a data directory for your postgres server.

> mkdir -p ~/Documents/personal/postgres/data

Then initialize that directory with the postgres configuration files. This is easily done 
by using the initdb command.

> initdb -D ~/Documents/personal/postgres/data


Now change directory to the parent folder of your `postgres` directory 

> cd ~/Documents/personal

It is time to create a bash file to store environment variables and alias.

> vim postgres/init

```
export PGDATA='/Users/shashank/Documents/personal/postgres/data'
export PGHOST=localhost
alias start-pg='pg_ctl -l $PGDATA/server.log start'
alias stop-pg='pg_ctl stop -m fast'
alias show-pg-status='pg_ctl status'
alias restart-pg='pg_ctl reload'
```

Please source your bash commands to the current console session.

> . postgres/init

Start up the server!
> start-pg
server starting
 
Observe the logs.
 
> tail -f postgres/data/server.log
LOG:  database system is ready to accept connections
LOG:  autovacuum launcher started
 
Your nice alias to see the postgres server status will be handy now.
 
> show-pg-status
pg_ctl: server is running (PID: 14845)
/usr/local/Cellar/postgresql/9.4.3/bin/postgres

Postgres sql it might not allow you to access currently, since you need a database with the username by which
 you install postgres
> psql
psql: FATAL:  database "shashank" does not exist

Not a problem ! Easily done by this command.

> createdb

Login to psql running on hostname localhost

> psql -h localhost
psql (9.4.3)
Type "help" for help.

shashank=#
 
-----

