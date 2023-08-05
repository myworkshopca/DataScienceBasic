# Assignment displaying airport data

This assignment will use SQLite as the database and query the database to show some results.

## install and test sqlite

```bash
sqlite3 --help
sqlite3 --version
``` 

## get ready the db file

download from github, store in data folder.

```bash
cd ~/rd/myworkshopca/DataScienceBasic/data; ls -la
```

## test the db file

```bash
sqlite3 ~/rd/myworkshopca/DataScienceBasic/data/airports.db "select * from cities limit 10"

# uset table format for output
sqlite3 -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db "select * from cities limit 10"
sqlite3 -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db "select * from airports limit 10"
```

## execute sql from a file

get ready the sql statements

```sql
-- comments here
select * from cities limit 5;
select * from airports limit 5;
```

Save it to a temp file
```vim
'<,'>!w /tmp/search.sql
```

check the saved temp file.
```bash
cat /tmp/search.sql
```

execute the sql file for the sqlite database
```bash
# -echo will print input sql before execute.
sqlite3 -echo -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db < /tmp/search.sql
```

### put them all together

vim map to execute sqlite

One command to do:
- save the selected lines into tmp sql file
- execute the temp sql file
- save the result in another temp file
- view the out temp file ina vert mode.

```vim
vnoremap \lq :w! /tmp/search.sql<CR>:!sqlite3 -echo -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db < /tmp/search.sql > /tmp/result<CR>:vert new /tmp/result<CR>

vnoremap \lq :!w /tmp/search.sql <CR> :exec "!sqlite3 -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db < /tmp/search.sql"<CR>

vnoremap \lq y:!echo <c-r>" > /tmp/search.sql; sqlite3 -table ~/rd/myworkshopca/DataScienceBasic/data/airports.db < /tmp/search.sql > /tmp/result<CR>:vert new /tmp/result<CR>
```

## assignment and answers

all city names in cities table.

```sql
-- show table structure
-- Notice that there is no semicolon (;) after the table name.
-- If you add a semicolon (;), the .schema will consider the albums;
-- as the table name and returns nothing because the table albums;
-- does not exist.
.schema cities

select distinct city from cities;

-- show all countries
select country from cities;
select distinct country from cities;
```

All cities in Ireland in cities table 

```sql
select city from cities where country='Ireland';
```

All airport names with their city and country

```sql
```

All aireports in London Unitied Kingdom

```sql
```
