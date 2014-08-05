# MySQL

SQL is a language all of its own, this is a rough guide to setting some simple stuff up.

## Access

    mysql -u <user> -p

### Browsing

* `show databases;` - shows databases.
* `use <database name>` - select database.
* `show tables;` - shows tables of selected database.

## Definition

### Database creation

    create database <database name>;

### Basic table creation

    create table <table name> (
       <name> <datatype>(<length>) <options>,
       primary(<id>),
       unique(<id>)
    );



